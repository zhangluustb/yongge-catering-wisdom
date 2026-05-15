# Agent 部署指南

> 如何把「勇哥灯塔」餐饮 AI 顾问部署起来，让更多创业者受益

---

## 方式一：接入 RAG 平台（推荐新手使用）

### 支持的平台

- **Dify**（dify.ai）
- **FastGPT**（fastgpt.in）
- **RagFlow**
- 或任何支持 Markdown 知识库导入的 RAG 平台

### 部署步骤

1. **注册/登录** RAG 平台
2. **创建知识库**：将 `knowledge/` 目录下所有 `.md` 文件上传
3. **创建应用**：选择"对话型应用"
4. **设置系统提示词**：将 `prompts/system_prompt.md` 的内容粘贴为系统提示词
5. **关联知识库**：将刚创建的知识库关联到应用
6. **测试对话**：用以下测试问题验证效果

### 测试对话示例

```
用户：我在郑州开了个串串火锅，170平，6个人，一天卖700，月租7500，怎么看？
期望：Agent 应该计算出月亏约1.8万，指出盈亏平衡点，建议减人并评估位置
```

```
用户：我想加盟一个汉堡品牌，加盟费6万，他们说是某知名品牌的股东出来做的
期望：Agent 应该立刻提示快招风险，列出快招识别清单
```

---

## 方式二：使用大模型 API 直接调用

### 使用 DeepSeek / 通义千问 / GPT-4o

```python
import requests
import json
from pathlib import Path

API_KEY = "你的API密钥"
# DeepSeek: https://api.deepseek.com/v1/chat/completions
# 通义千问: https://dashscope.aliyuncs.com/api/v1/services/aigc/text-generation/generation
API_URL = "https://api.deepseek.com/v1/chat/completions"

# 加载系统提示词和知识库
system_prompt = Path("prompts/system_prompt.md").read_text(encoding="utf-8")
knowledge_files = [
    "knowledge/01_business_model.md",
    "knowledge/02_location_strategy.md",
    "knowledge/03_operations_guide.md",
    "knowledge/04_traps_and_turnaround.md",
]
knowledge_content = "\n\n".join(
    Path(f).read_text(encoding="utf-8") for f in knowledge_files
)

full_system_prompt = f"""{system_prompt}

---以下是你的知识库---

{knowledge_content}
"""


def chat(user_message: str, history: list | None = None) -> tuple[str, list]:
    if history is None:
        history = []

    messages = [{"role": "system", "content": full_system_prompt}]
    messages.extend(history)
    messages.append({"role": "user", "content": user_message})

    response = requests.post(
        API_URL,
        headers={
            "Authorization": f"Bearer {API_KEY}",
            "Content-Type": "application/json",
        },
        json={
            "model": "deepseek-chat",
            "messages": messages,
            "temperature": 0.6,
            "max_tokens": 2048,
        },
        timeout=60,
    )

    result = response.json()
    reply = result["choices"][0]["message"]["content"]
    history.append({"role": "user", "content": user_message})
    history.append({"role": "assistant", "content": reply})
    return reply, history


if __name__ == "__main__":
    print("=== 勇哥灯塔 · 餐饮创业AI顾问 ===")
    print("输入 'quit' 退出\n")

    history = []
    while True:
        user_input = input("你: ")
        if user_input.lower() == "quit":
            break
        reply, history = chat(user_input, history)
        print(f"\n顾问: {reply}\n")
```

### 其他推荐模型

- **DeepSeek**（推荐，中文能力强，成本低）
- **通义千问**
- **智谱 GLM**
- **MiniMax M2.7**
- **OpenAI GPT-4o**（需科学上网）

---

## 方式三：接入微信 / 钉钉

### 接入微信（通过 Dify + 微信机器人）

1. 在 Dify 部署好 Agent 并获取 API 端点
2. 使用开源微信机器人框架（如 `chatgpt-on-wechat`）接入
3. 配置 API 地址和 Token，微信群中 @机器人 即可对话

### 接入钉钉

1. 钉钉支持自建机器人
2. 将 Agent API 接入钉钉自建 Webhook
3. 在钉钉群中 @机器人 对话

---

## 效果优化建议

1. **分块导入知识库**：建议按文件分块，chunk size 设为 500-800 字符，overlap 100
2. **调整温度参数**：建议 temperature 设为 0.5-0.6，保持回答稳健
3. **开场白设计**：建议设置开场白，引导用户提供六问诊断所需信息
4. **定期更新**：每年更新知识库中的典型案例数据

---

## 免责声明

- 本 Agent 为开源项目，仅供学习参考
- 不构成正式商业建议，实际经营决策请结合当地市场实际情况综合判断
- 与勇哥本人及其团队无商业关联
