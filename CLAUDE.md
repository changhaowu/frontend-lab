# frontend-lab

前端实验场 — 给设计师朋友的 Claude Code 演示项目。

---

## 这是什么？

这个项目用来演示如何用 **Claude Code**（AI 编程助手）做前端设计开发。特别适合设计师理解：AI 工具里的 **Skill（技能）** 和 **Agent（智能体）** 是什么、能做什么。

---

## Skill vs Agent — 一句话区别

| 概念 | 类比 | 作用 |
|------|------|------|
| **Skill（技能）** | 一本专业手册 | 告诉 AI "你在做这件事时，要遵循这些知识/规则" |
| **Agent（智能体）** | 一个专门的同事 | 一个独立的 AI 角色，有自己的目标，能独立完成任务 |

### Skill 更详细的解释

Skill 是**项目级别的知识注入**。当你在这个项目里跟 Claude 对话时，它会自动读取 `.claude/skills/` 下面的内容，相当于提前告诉 AI：

> "我们在做前端设计，这里有 67 种 UI 风格、161 套配色方案、57 组字体搭配……你生成代码时请参考这些。"

不需要你每次手动说"请参考 glassmorphism 风格"，AI 已经知道了。

### Agent 更详细的解释

Agent 是**有独立任务能力的 AI**。你可以叫它去：

- 自主搜索信息、读文件、写代码
- 完成一个多步骤任务（比如"把这个设计稿变成可运行的网页"）
- 在后台并行执行，不需要你一直盯着

在 Claude Code 里，Agent 通过 `.claude/agents/` 目录定义，或者通过 `/agent` 命令召唤。

---

## 本项目已安装的 Skill

### ui-ux-pro-max

> AI 驱动的设计智能库，覆盖 13 种主流前端技术栈。

**包含内容：**
- 67 种 UI 风格（glassmorphism、brutalism、neumorphism、bento grid……）
- 161 套配色方案（按行业/产品类型分类）
- 57 组字体搭配（含 Google Fonts 导入代码）
- 25 种图表类型推荐
- 99 条 UX 最佳实践
- 支持栈：React、Next.js、Vue、Svelte、Tailwind、shadcn/ui、SwiftUI、Flutter……

**怎么用：** 直接跟 Claude 说你要做什么就行，不需要额外指令。

```
"帮我做一个 SaaS 产品的 landing page，风格现代简洁"
"给这个 dashboard 推荐一套深色配色方案"
"用 glassmorphism 风格做一个登录卡片，React + Tailwind"
"检查这段代码的 accessibility 问题"
```

---

## 快速开始

```bash
# 1. 安装依赖（搜索功能用 Python）
# 无需额外安装，Python 3 即可

# 2. 打开 Claude Code
claude

# 3. 直接描述你想要的 UI
```

---

## 目录结构

```
frontend-lab/
├── CLAUDE.md                    ← 你现在看的这个文件
├── .claude/
│   └── skills/
│       └── ui-ux-pro-max/       ← 设计智能 skill
│           ├── SKILL.md         ← skill 主文件（AI 自动读取）
│           ├── data/            ← CSV 格式的设计知识库
│           └── scripts/         ← Python 搜索引擎
└── (你的前端项目文件)
```

---

## 给设计师的提示

1. **不需要懂代码** 也能描述你想要的效果，Claude 会生成可运行的代码
2. **可以上传设计稿** 说"按这个设计稿实现"，Claude 会读图生成代码
3. **风格词直接用** glassmorphism、neumorphism、bento grid 这些词 Claude 都认识
4. **迭代很方便** 说"把背景色改深一点"、"加一个 hover 动效" 就够了
