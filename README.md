# 勇哥餐饮智慧 —— 让每一个创业者少走弯路

> **"你亏钱不是因为你不努力，是因为你没做对模型。"** —— 勇哥

---

## 这是什么

勇哥（蔡勇）是 B 站知名餐饮连麦博主，创作了 600+ 期真实的餐饮创业诊断视频。他以犀利直白的风格，帮助无数在餐饮路上踩坑的创业者分析问题、找到出路。

本项目从勇哥 600+ 期原创视频字幕中提取核心知识，构建一个开源的**餐饮创业智慧知识库**和 **AI 顾问 Agent**。

让更多想做餐饮的普通人，能在投钱之前就知道哪些坑不能踩。

---

## 项目内容

### 关于勇哥

- [勇哥简介与创作理念](./tribute/biography.md) — 了解这位"餐饮连麦诊断师"
- [勇哥经典语录与餐饮理念](./tribute/quotes_and_philosophy.md) — 那些让创业者醍醐灌顶的话

### 知识库（餐饮创业 · 经营诊断 · 避坑指南）

- [生意模型与选品策略](./knowledge/01_business_model.md) — 什么模型才能回本？怎么算才不亏？
- [选址策略与商圈分析](./knowledge/02_location_strategy.md) — 位置选错一切白费，怎么看商圈？
- [运营实战与成本控制](./knowledge/03_operations_guide.md) — 开业之后如何活下去？
- [避坑指南与翻身案例](./knowledge/04_traps_and_turnaround.md) — 快招怎么识别？被坑了如何自救？

### AI Agent（勇哥餐饮顾问）

- [系统提示词](./prompts/system_prompt.md) — Agent 的灵魂：诊断框架 + 风格指引
- [Agent 部署说明](./agent/README.md) — 如何部署你自己的"勇哥 AI 顾问"

---

## 快速开始

### 方式一：直接阅读知识库

进入 `knowledge/` 目录，按需阅读。所有内容以 Markdown 格式编写，手机、电脑均可直接查看。

### 方式二：部署 AI Agent

将 `knowledge/` 下所有文件导入 RAG 平台（如 Dify、FastGPT、RagFlow 等），使用 `prompts/system_prompt.md` 作为系统提示词，即可构建自己的餐饮创业 AI 顾问。

详见 [Agent 部署说明](./agent/README.md)。

---

## 项目结构

```
yongge-catering-wisdom/
├── README.md                              # 你正在读的文件
├── LICENSE                                # CC BY 4.0
├── CONTRIBUTING.md                        # 贡献指南
│
├── tribute/                               # 关于勇哥
│   ├── biography.md                       # 勇哥简介与创作背景
│   └── quotes_and_philosophy.md           # 经典语录与餐饮理念
│
├── knowledge/                             # 核心知识库
│   ├── 01_business_model.md               # 生意模型与选品策略
│   ├── 02_location_strategy.md            # 选址策略与商圈分析
│   ├── 03_operations_guide.md             # 运营实战与成本控制
│   └── 04_traps_and_turnaround.md         # 避坑指南与翻身案例
│
├── prompts/                               # AI Agent 提示词
│   └── system_prompt.md                   # 系统提示词
│
├── agent/                                 # Agent 部署相关
│   └── README.md                          # 部署指南
│
└── .github/
    └── ISSUE_TEMPLATE/
        └── suggestion.md                  # 案例提交模板
```

---

## 知识来源

本项目知识库基于勇哥 B 站频道 [勇哥餐饮原创](https://space.bilibili.com/3546801669933097) 的 600+ 期真实连麦视频字幕提炼整理，涵盖 2024-2026 年的真实创业案例。

> 所有知识内容为社区原创整理表述，基于勇哥公开视频内容进行提炼和归纳，不直接复制原视频台词。

---

## 声明

- 本项目为个人学习整理，与勇哥本人及其团队无任何商业关联。
- 知识库内容仅供学习参考，不构成任何形式的正式商业建议。
- 实际经营决策请结合当地市场实际情况综合判断。
- 如有侵权，请联系删除。

---

## 致勇哥

勇哥，你用几百期连麦，陪着那些已经踩进坑里的人一起想办法。你从来不说废话，直接问：一天卖多少？毛利率多少？租金多少？几个人？

你让那些不知道哪里出了问题的人，第一次看清了自己生意的真实状况。

你帮过的每一个创业者，他们少亏的每一分钱，就是你留在这个世界上最好的作品。

---

## 许可证

- 知识内容（`knowledge/`、`prompts/`、`tribute/`）：[CC BY 4.0](./LICENSE) — 署名即可自由使用
- 欢迎任何人 fork、分享、改进，让更多人受益

*"餐饮不难，难的是大多数人在入行之前根本不知道规则。"* —— 勇哥
