# learn-repo — 从开源项目生成系统性学习教程 + 面试全家桶

## 触发条件

当用户提供一个开源项目名称/URL 并要求生成系统性学习教程时使用。

触发词：
- "learn this repo: <项目名/URL>"
- "帮我生成这个仓库的学习教程"
- "给这个项目做教程"

## 输入与输出

### 输入
- **必须**：开源项目名（如 `minimind`）或 GitHub URL（如 `https://github.com/jingyaogong/minimind`）
- **可选**：目标语言（默认中文）、课程深度

### 输出（完整交付物）

| 交付物 | 数量 | 说明 |
|--------|------|------|
| **课程教程** | 20 课 | docs/L01~L20.md，由浅入深 |
| **面试八股文** | 5-10 文件 | interview/06~10，深度拷问题集 |
| **STAR 面试稿** | 1 文件 | docs/L<N>-STAR面试法完整稿.md |
| **简历模板** | 1 文件 | docs/L<N>-简历撰写指南.md |
| **项目介绍话术** | 1 文件 | interview/01-项目介绍话术.md |
| **分类面试题** | 4 文件 | interview/02~05，按方向分类 |
| **哆啦A梦漫画** | 12-15 张 | assets/comics/，每张配合一课 |
| **Web 站点** | 1 套 | Next.js SSG，含首页+课程+面试 |
| **构建脚本** | 2 个 | HTML + PDF 导出 |

---

## 两步执行法

### 第一步：生成 CLAUDE.md（大纲 + Todo）

先生成项目的 CLAUDE.md 文件，包含完整大纲和任务清单。这是整个项目的"施工蓝图"。

### 第二步：循环迭代实现

基于 CLAUDE.md 中的 Todo List，逐项实现，每完成一项就更新状态。

---

## 第一步详细说明：生成 CLAUDE.md

### 1.1 研究源项目

```bash
# 克隆源仓库
git clone --depth 1 <REPO_URL> /tmp/source-repo
```

使用 Explore agent 并行分析：
1. Agent A: 项目架构 & 核心模块（README、目录结构、核心文件）
2. Agent B: 核心算法 & 数据结构（关键实现）
3. Agent C: 构建流程 & 技术栈（依赖、运行方式）

### 1.2 CLAUDE.md 模板

根据分析结果，生成如下格式的 CLAUDE.md：

```markdown
（交流可以用英文，本文档中文，保留这句）

# <项目名称> 学习教程项目说明

## 项目目标
编写一份 <项目名称> 的由浅入深学习教程，包含 20 节课程、面试八股文、
STAR 面试稿、简历模板和哆啦A梦漫画图解。

## 工具说明
当需要时，可以通过深度研究得到想要的答案

## 源项目信息
- 项目名：<名称>
- 地址：<URL>
- Star 数：<N>k+
- 技术栈：<语言/框架>
- 核心功能：<一句话描述>

## 教程大纲

### 第一部分：基础入门（L01-L04）
1. **<领域>简介与发展历程**
   - 1.1 什么是<核心概念>
   - 1.2 <概念A> vs <概念B> vs <概念C>
   - 1.3 应用场景
   - 1.4 主流<领域>架构概览
   - 习题集1

2. **<基础理论>**
   - 2.1 ...
   - 习题集2

3. **<工具/语言>快速上手**
   - 3.1 ...
   - 习题集3

4. **<项目名>项目导览**
   - 4.1 目录结构
   - 4.2 核心文件解读
   - 4.3 环境搭建与首次运行
   - 习题集4

### 第二部分：核心组件拆解（L05-L10）
5-10. **逐个拆解项目的核心模块**
   - 每个模块一课
   - 从简单到复杂

### 第三部分：完整流程（L11-L15）
11-15. **端到端流程串联**

### 第四部分：高级特性与面试（L16-L20）
16-18. **高级功能 & 优化 & 部署**
19. **简历撰写指南**
20. **STAR 面试法完整稿**

## 面试材料大纲

### 基础面试（interview/01-05）
- 01-项目介绍话术.md（30秒/1分钟/3分钟）
- 02-<方向A>面试题.md
- 03-<方向B>面试题.md
- 04-<方向C>面试题.md
- 05-综合追问与深挖题.md

### 深度八股文（interview/06-10）
- 06-<核心技术A>深度拷问30题.md
- 07-<核心技术B>面试50题.md
- 08-<核心技术C>面试30题.md
- 09-工程实践面试30题.md
- 10-<项目名>专属面试50题.md

## 哆啦A梦漫画规划

| 编号 | 文件名 | 对应课程 | 漫画主题 |
|------|--------|---------|---------|
| 01 | 01-<概念>.png | L01/L02 | <领域>全景概览图 |
| 02 | 02-<组件>.png | L05 | <组件>工作原理 |
| ... | ... | ... | ... |
| 12-15 | ... | L16-L18 | <高级特性> |

## 教程特色
- 每章节包含理论讲解、实例分析、代码示例
- 大量习题覆盖概念理解、设计实践、问题解决
- 渐进式学习路径，从基础到高级
- 面试八股文 190+ 题，覆盖项目所有知识点
- STAR 面试稿 + 简历模板，直接用于求职
- 哆啦A梦漫画图解，降低学习门槛

## 任务清单 (Todo List)

### Phase 1: 基础设施 🏗️
- [ ] 创建项目目录结构
- [ ] 初始化 Next.js Web 应用
- [ ] 创建 CLAUDE.md（本文件）
- [ ] 创建 README.md

### Phase 2: 课程内容 📚
- [ ] 编写 L01-<标题>.md
- [ ] 编写 L02-<标题>.md
- [ ] ...（每课一个 todo）
- [ ] 编写 L20-<标题>.md

### Phase 3: 面试材料 🎯
- [ ] 编写 interview/01-项目介绍话术.md
- [ ] 编写 interview/02-<方向A>面试题.md
- [ ] 编写 interview/03-<方向B>面试题.md
- [ ] 编写 interview/04-<方向C>面试题.md
- [ ] 编写 interview/05-综合追问与深挖题.md
- [ ] 编写 interview/06-<核心技术>深度拷问30题.md
- [ ] ...
- [ ] 编写 interview/10-<项目名>专属面试50题.md

### Phase 4: 哆啦A梦漫画 🎨
- [ ] 生成漫画 01-<主题>.png
- [ ] 生成漫画 02-<主题>.png
- [ ] ...（每张一个 todo）

### Phase 5: Web 应用 🌐
- [ ] 创建 lib/lessons-data.ts
- [ ] 创建 lib/interview-data.ts
- [ ] 创建首页 + Hero 组件
- [ ] 创建课程列表页
- [ ] 创建课程详情页
- [ ] 创建面试列表页
- [ ] 创建面试详情页
- [ ] 验证 npm run build

### Phase 6: 构建脚本 🔧
- [ ] 创建 scripts/build_html.py
- [ ] 创建 scripts/build_pdf.py

### Phase 7: 收尾 ✅
- [ ] 质量检查
- [ ] git init && commit

# important-instruction-reminders
Do what has been asked; nothing more, nothing less.
NEVER create files unless they're absolutely necessary for achieving your goal.
ALWAYS prefer editing an existing file to creating a new one.
NEVER proactively create documentation files (*.md) or README files.
Only create documentation files if explicitly requested by the User.
```

---

## 第二步详细说明：循环迭代实现

基于 CLAUDE.md 的 Todo List，按 Phase 顺序逐项实现。

### 2.1 课程内容生成

#### 每课 Markdown 模板

```markdown
# L<NN> - <课程标题>

> **"<一句诗意/比喻性的引语>"**

---

## 📌 本节目标

1. <目标1：了解/理解/掌握 + 具体内容>
2. <目标2>
3. <目标3>

---

## 📚 前置知识

- <需要先知道的知识点1>
- <不需要XXX基础（降低心理门槛）>

---

## 正文讲解

### 1. <第一个概念>——<用类比引出>

<用生活化的比喻引入概念>

> **类比**：<将技术概念比喻为日常事物>

<正式定义和解释>

#### 1.1 <子概念>

<详细讲解，穿插代码示例>

### 2. <第二个概念>

<...同样的模式...>

---

## 💡 本节小结

| 概念 | 一句话总结 |
|------|-----------|
| <概念1> | <简洁总结> |

---

> 下一课我们将学习 **L<NN+1> - <下一课标题>**
```

#### 写作风格

| 维度 | 要求 |
|------|------|
| **语气** | 对话式、亲切、不居高临下 |
| **类比** | 每个新概念必须有日常生活类比 |
| **数学** | 公式前后必须有直觉解释；用 KaTeX `$$...$$` |
| **代码** | 关键代码片段（非完整文件）；必须有注释 |
| **表格** | 比较性内容优先用表格呈现 |
| **Emoji** | 标题用 📌📚💡🔗 标记 |
| **长度** | 每课 800-2000 字正文（不含代码） |

#### 课程分阶段颜色

| 阶段 | 定位 | 颜色 |
|------|------|------|
| Phase 1 (L01-L04) | 零基础入门 | 🟢 Green `#10b981` |
| Phase 2 (L05-L10) | 核心组件拆解 | 🔵 Blue `#3b82f6` |
| Phase 3 (L11-L15) | 完整流程串联 | 🟣 Purple `#8b5cf6` |
| Phase 4 (L16-L20) | 高级特性与面试 | 🟠 Orange `#f59e0b` |

### 2.2 面试八股文生成

#### 分类面试题模板（interview/02~05）

```markdown
# <NN> - <方向>面试题

> 覆盖 <技术领域> 的核心知识点，每题结合 <项目名> 的具体实现。

---

## Q1: <问题>

**标准答案：**

<结构化回答，3-5 段>

<如有公式>：
$$<公式>$$

| 对比项 | 方案A | 方案B |
|--------|-------|-------|
| ... | ... | ... |

**<项目名>中的实现：**

```<language>
// 源码片段 + 注释
```

**追问方向：**
- <可能的追问1>
- <可能的追问2>
```

#### 深度拷问题集模板（interview/06~10）

每个文件 30-50 题，格式同上但更深入：
- 必须包含公式推导
- 必须包含源码对照
- 必须包含"追问方向"
- 题目难度标记：⭐基础 / ⭐⭐进阶 / ⭐⭐⭐深入

### 2.3 STAR 面试稿生成

#### 文件：docs/L<N>-STAR面试法完整稿.md

```markdown
# L<N> - STAR 面试法完整稿

## 一、STAR 面试法介绍

### 1.1 什么是 STAR 面试法？

| 要素 | 英文 | 含义 | 核心问题 |
|------|------|------|----------|
| **S** | Situation | 情境/背景 | 当时的环境和上下文是什么？ |
| **T** | Task | 任务/目标 | 你需要解决什么问题？ |
| **A** | Action | 行动/措施 | 你具体做了什么？ |
| **R** | Result | 结果/成效 | 最终效果如何？ |

### 1.2 黄金比例
S（10%）→ T（10%）→ A（60%）→ R（20%）

## 二、自我介绍模板

### 2.1 30秒版本（电梯演讲）
> 面试官好，我叫XXX... 我独立完成了<项目名>项目...
> <一段话：做了什么+技术+成果>

### 2.2 1分钟版本（常规面试）
> **架构方面**，...
> **训练/实现方面**，...
> **成果方面**，...

### 2.3 3分钟版本（深入介绍）
> <背景 + 架构 + 技术细节 + 挑战与解决 + 成果与反思>

## 三、技术难点 STAR 应对（7个场景）

### 场景1: <技术难点名称>

**S（背景）**：在<项目名>项目中，...
**T（任务）**：需要解决...
**A（行动）**：
1. 首先...
2. 然后...
3. 最后...
**R（结果）**：
- 量化指标1
- 量化指标2

### 场景2-7: ...（同样格式）

## 四、模拟面试（12轮）

### 第1轮：项目介绍
**面试官**：介绍一下你的<项目名>项目？
**你**：<参考30秒/1分钟版本>
**面试官追问**：<追问>
**你**：<应对>

### 第2-12轮: ...
```

### 2.4 简历模板生成

#### 文件：docs/L<N>-简历撰写指南.md

```markdown
# L<N> - <项目名> 简历撰写指南

## 一、STAR 法则在简历中的应用

| 要素 | 简历体现 | 示例 |
|------|---------|------|
| S | 一句话背景 | <领域>门槛高... |
| T | 融入标题 | 从零实现... |
| A | 每个 bullet | 实现了..., 完成了... |
| R | 量化收尾 | <N>参数, <指标> |

## 二、简历描述（4个详略等级）

### 精简版（1行）
```
<项目名> - <一句话描述>
```

### 标准版（2-3行）
```
<项目名> - <副标题>                        20xx.xx - 20xx.xx
• <核心工作描述，含技术关键词>
• <成果，含量化数据>
```

### 详细版（4-5行）
```
<多行描述，分：架构/实现/优化/成果>
```

### 完整版（6-8行，含量化数据）
```
<完整版，每行一个维度>
```

## 三、量化数据对照表

| 维度 | 量化示例 |
|------|---------|
| <维度1> | <数据> |
| ... | ... |

## 四、普通写法 vs 优化写法（6组对比）

| 模糊描述 | 精准描述 |
|----------|----------|
| "实现了xxx功能" | "用xxx技术实现了xxx，性能提升xx%" |
| ... | ... |

## 五、不同岗位方向调整（4个方向）

### 方向1: <岗位A>
重点突出：...

### 方向2-4: ...
```

### 2.5 项目介绍话术生成

#### 文件：interview/01-项目介绍话术.md

```markdown
# 01 - 项目介绍话术

## 🎯 30秒电梯演讲
<一段话概括>

## 🎤 1分钟常规面试版本
<扩展版>

## 📋 3分钟深入介绍
<详细版>

## 💡 面试技巧

| 场景 | 建议 |
|------|------|
| 面试官频频点头 | 继续深入技术细节 |
| 面试官皱眉 | 换用更通俗的类比 |
| 被打断 | 直接跳到 Result |
| 被追问细节 | 切换到 STAR 模式 |
```

### 2.6 哆啦A梦漫画生成

#### 漫画风格规范

- **角色**：哆啦A梦（讲解者）+ 大雄（学习者）
- **场景**：大雄的房间/学校教室/户外
- **布局**：宽幅横图（16:9），标题在顶部
- **元素**：技术概念用道具/黑板/全息投影呈现
- **对话泡**：大雄提问 + 哆啦A梦解答
- **标注**：关键术语用箭头+文字标注

#### 生成 Prompt 模板

对每张漫画，使用如下 prompt 生成（通过 DALL-E / 图片生成工具）：

```
Create a Doraemon-style educational comic illustration in wide format (16:9).

Title at top: "<中文标题>"

Scene: <场景描述，如"大雄的房间">

Characters:
- Doraemon (blue robot cat) is presenting/explaining <概念>
- Nobita (大雄, boy with glasses) is watching with amazement

Visual elements:
- <技术概念的视觉化描述>
- <用道具/图表/投影展示的内容>
- Chinese text labels pointing to key components: "<标注1>", "<标注2>", ...

Speech bubble from Nobita: "<惊叹语，如'原来xxx是这样的！'>"

Style: Bright, colorful, educational manga style, clean lines,
warm indoor lighting, detailed background
```

#### 漫画命名规则

```
assets/comics/
├── 01-<主题缩写>.png    # 对应 L01/L02 全景概览
├── 02-<组件名>.png      # 对应 L05 第一个核心组件
├── 03-<组件名>.png      # 对应 L06
├── ...
└── 15-<主题>.png        # 对应完整流程
```

### 2.7 Web 应用搭建

#### 项目目录结构

```
learn-<REPO_NAME>/
├── README.md
├── CLAUDE.md                # 项目说明 + Todo
├── LICENSE
├── docs/                    # 20 课 Markdown
│   ├── L01-<标题>.md
│   ├── ...
│   ├── L19-简历撰写指南.md
│   └── L20-STAR面试法完整稿.md
├── interview/               # 10 个面试文件
│   ├── 01-项目介绍话术.md
│   ├── ...
│   └── 10-<项目名>专属面试50题.md
├── assets/
│   └── comics/              # 12-15 张哆啦A梦漫画
├── scripts/
│   ├── build_html.py
│   └── build_pdf.py
└── web/                     # Next.js SSG
    ├── package.json
    ├── next.config.ts        # output: "export"
    └── src/
        ├── app/
        │   ├── globals.css
        │   ├── layout.tsx
        │   ├── page.tsx
        │   ├── learn/page.tsx
        │   ├── lesson/[slug]/page.tsx
        │   ├── interview/page.tsx
        │   └── interview/[slug]/page.tsx
        ├── components/
        │   ├── SiteNav.tsx
        │   ├── Hero.tsx
        │   ├── LearningPath.tsx
        │   ├── MarkdownArticle.tsx
        │   ├── CodeBlock.tsx
        │   ├── InterviewPreview.tsx
        │   └── Footer.tsx
        └── lib/
            ├── lessons-data.ts
            ├── interview-data.ts
            ├── readMarkdown.ts
            └── mdTitle.ts
```

#### 核心代码模板

**next.config.ts**
```typescript
import type { NextConfig } from "next";
const nextConfig: NextConfig = {
  output: "export",
};
export default nextConfig;
```

**lib/lessons-data.ts**
```typescript
export const LESSON_FILES: Record<string, string> = {
  L01: "L01-<标题>.md",
  // ...根据大纲生成 L01-L20
};

export const LESSON_ORDER = [
  "L01", "L02", /* ... */ "L20",
] as const satisfies readonly (keyof typeof LESSON_FILES)[];

export type LessonSlug = keyof typeof LESSON_FILES;
```

**lib/interview-data.ts**
```typescript
export const INTERVIEW_FILES: Record<string, string> = {
  "01": "01-项目介绍话术.md",
  // ...10 个文件
};

export const INTERVIEW_META: Record<string, { title: string; subtitle: string }> = {
  "01": { title: "项目介绍话术", subtitle: "30秒/1分钟/3分钟版本" },
  // ...
};

export const INTERVIEW_ORDER = ["01", "02", "03", "04", "05"] as const;
```

**lib/readMarkdown.ts**
```typescript
import fs from "fs";
import path from "path";

export function readLessonMarkdown(slug: string): string {
  const { LESSON_FILES } = require("./lessons-data");
  const filename = LESSON_FILES[slug];
  if (!filename) throw new Error(`Unknown lesson slug: ${slug}`);
  return fs.readFileSync(path.join(process.cwd(), "..", "docs", filename), "utf-8");
}

export function readInterviewMarkdown(slug: string): string {
  const { INTERVIEW_FILES } = require("./interview-data");
  const filename = INTERVIEW_FILES[slug];
  if (!filename) throw new Error(`Unknown interview slug: ${slug}`);
  return fs.readFileSync(path.join(process.cwd(), "..", "interview", filename), "utf-8");
}
```

**app/lesson/[slug]/page.tsx**
```tsx
import { LESSON_FILES, LESSON_ORDER } from "@/lib/lessons-data";
import { readLessonMarkdown } from "@/lib/readMarkdown";
import { titleFromMarkdown } from "@/lib/mdTitle";
import { MarkdownArticle } from "@/components/MarkdownArticle";
import Link from "next/link";

export function generateStaticParams() {
  return Object.keys(LESSON_FILES).map((slug) => ({ slug }));
}

export default async function LessonPage({
  params,
}: {
  params: Promise<{ slug: string }>;
}) {
  const { slug } = await params;
  const raw = readLessonMarkdown(slug);
  const title = titleFromMarkdown(raw);
  const idx = LESSON_ORDER.indexOf(slug as any);
  const prev = idx > 0 ? LESSON_ORDER[idx - 1] : null;
  const next = idx < LESSON_ORDER.length - 1 ? LESSON_ORDER[idx + 1] : null;

  return (
    <main className="max-w-3xl mx-auto px-4 py-16">
      <Link href="/learn">← 返回课程目录</Link>
      <h1>{title}</h1>
      <MarkdownArticle content={raw} />
      <nav>
        {prev && <Link href={`/lesson/${prev}`}>← 上一课</Link>}
        {next && <Link href={`/lesson/${next}`}>下一课 →</Link>}
      </nav>
    </main>
  );
}
```

**components/MarkdownArticle.tsx**
```tsx
"use client";
import ReactMarkdown from "react-markdown";
import remarkGfm from "remark-gfm";

export function MarkdownArticle({ content }: { content: string }) {
  return (
    <article className="prose prose-invert max-w-none">
      <ReactMarkdown remarkPlugins={[remarkGfm]}>{content}</ReactMarkdown>
    </article>
  );
}
```

#### 设计系统

```css
:root {
  --bg-primary: #0a0a0f;
  --bg-secondary: #12121a;
  --bg-card: #1a1a2e;
  --text-primary: #e4e4e7;
  --text-secondary: #a1a1aa;
  --accent-purple: #8b5cf6;
  --phase-green: #10b981;
  --phase-blue: #3b82f6;
  --phase-purple: #8b5cf6;
  --phase-orange: #f59e0b;
}
```

#### 依赖

```json
{
  "dependencies": {
    "framer-motion": "^12",
    "lucide-react": "^0.564",
    "next": "^15",
    "react": "^19",
    "react-dom": "^19",
    "react-markdown": "^10",
    "remark-gfm": "^4"
  },
  "devDependencies": {
    "@tailwindcss/postcss": "^4",
    "tailwindcss": "^4",
    "typescript": "^5"
  }
}
```

### 2.8 README.md 模板

```markdown
<p align="center">
  <h1 align="center">Learn <项目名></h1>
  <p align="center">
    <em>从零基础到面试通关 —— 20节课 + <N>道面试题 + 哆啦A梦图解</em>
  </p>
</p>

---

## 这个项目是什么？

> **用 20 节课 + <N> 道面试八股文 + <M> 张哆啦A梦漫画图解，
> 把零基础小白带到能在面试中自信讲述
> "我深入理解了<项目名>的每一个技术环节"的水平。**

[<项目名>](<URL>) 是 <一句话描述>，在 GitHub 上获得了 <N>k+ Star。
本仓库是 <项目名> 的 **系统化学习教程 + 面试备战手册**。

### 本项目的特色

| 特色 | 说明 |
|------|------|
| **<N>+ 面试题** | 八股文深度拷问，覆盖所有核心知识点 |
| **STAR 面试稿** | 30秒/1分钟/3分钟自我介绍 + 技术难点 STAR 应对 |
| **简历撰写指南** | 4 种详略版本 + 多岗位方向调整 |
| **哆啦A梦漫画** | <M> 张原创漫画图解核心概念 |
| **源码深度解析** | 关键模块源码逐行解读 |
| **多格式输出** | Markdown / HTML / PDF |

## 📖 课程目录

### Phase 1 · 零基础入门
| 课程 | 主题 | 格言 | 预计时长 |
|------|------|------|---------|
| L01 | ... | _"..."_ | 30min |
| ... | ... | ... | ... |

### Phase 2 · 核心组件拆解
（含漫画列）

### Phase 3 · 完整流程
（含漫画列）

### Phase 4 · 高级特性与面试
（含漫画列）

## 📋 面试宝典
（表格列出所有面试文件）

## 🎯 学习路线图
（ASCII 图 or 表格，3/7/14 天路径）

## 🎨 哆啦A梦图解
（展示几张代表性漫画缩略图）
```

---

## 质量检查清单

### 课程内容
- [ ] 每课有 📌本节目标、📚前置知识、正文、💡小结
- [ ] 每个技术概念有日常生活类比
- [ ] 代码示例有清晰注释
- [ ] 课程顺序由浅入深
- [ ] 前后课程有衔接语
- [ ] 总课数 = 20

### 面试材料
- [ ] 项目介绍话术有 30秒/1分钟/3分钟 三个版本
- [ ] 分类面试题 4 个方向、每方向 20+ 题
- [ ] 深度八股文 5 个专题、每专题 30-50 题
- [ ] 每题有标准答案 + 源码对照 + 追问方向
- [ ] 总题数 ≥ 190

### STAR 面试稿
- [ ] STAR 法则介绍完整
- [ ] 自我介绍 3 个版本
- [ ] 技术难点 STAR ≥ 7 个场景
- [ ] 模拟面试 ≥ 12 轮

### 简历模板
- [ ] 4 个详略等级
- [ ] 量化数据对照表
- [ ] 普通 vs 优化写法 ≥ 6 组对比
- [ ] ≥ 4 个岗位方向调整

### 哆啦A梦漫画
- [ ] 12-15 张漫画
- [ ] 每张对应一课核心概念
- [ ] 哆啦A梦(讲解)+大雄(学习)角色
- [ ] 中文标注清晰

### Web & 构建
- [ ] `npm run build` 零错误
- [ ] 上一课/下一课导航完整
- [ ] README 包含学习路线图
- [ ] build_html.py 可运行
- [ ] build_pdf.py 可运行

---

## 快速参考：CLAUDE.md 之后的执行顺序

```
1. CLAUDE.md 已生成 ✅
2. mkdir -p docs interview assets/comics scripts web
3. 逐课生成 docs/L01~L20.md（每完成一课更新 CLAUDE.md todo）
4. 生成 interview/01~10.md
5. 生成哆啦A梦漫画 assets/comics/01~15.png
6. 初始化 Next.js + 创建所有页面和组件
7. 创建 scripts/build_html.py + build_pdf.py
8. 生成 README.md
9. 全量质量检查
10. git init && git add -A && git commit
```