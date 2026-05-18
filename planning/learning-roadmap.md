# 学习路线规划

> 当前路线：以 **Full-stack AI / Agent Engineer** 为目标，用项目驱动学习，而不是按资料顺序刷课。

---

## 当前状态

- **背景**: 前端工程师，熟悉 TypeScript/JavaScript
- **现实工作**: 目前大量使用 Python
- **目标方向**: 全栈 AI / Agent 工程
- **不走路线**: 纯算法、模型训练、纯 AI 前端
- **核心策略**: 先落地 AI 应用，再深入 RAG、Tool Calling、Agent Workflow 和工程化
- **开始时间**: 2026年5月

---

## 职业目标

目标不是“会用 AI”，而是：

> 能把 AI 系统做成可靠产品，具备 RAG、工具调用、工作流编排、Agent 状态管理、评估、可观测性和部署能力。

更具体的岗位定位：

- Full-stack AI Engineer
- AI Application Engineer
- AI Agent Engineer
- LLM Application Engineer
- Agent Workflow Engineer

---

## 路线总览

```text
Python / TS AI 应用基础
        ↓
RAG 与资料库工程
        ↓
Tool Calling 与工作流
        ↓
Agent 状态管理与 LangGraph
        ↓
生产化：评估、观测、安全、部署
        ↓
作品集：可展示、可复盘、可面试讲解
```

---

## 阶段 0：路线收敛与资料筛选

**目标**: 明确方向，避免被大而全资料拖住。

**当前状态**: 进行中

**核心任务**:

- [x] 明确不走纯算法/模型训练路线
- [x] 明确不做纯 AI 前端壳子
- [x] 将目标定位为 Full-stack AI / Agent Engineer
- [x] 将资料分为实操类、理论类、查漏类
- [ ] 建立“暂不学习清单”
- [ ] 持续记录路线决策过程

**产出文档**:

- `planning/career-positioning.md`
- `planning/reference-notes.md`
- `planning/learning-roadmap.md`

---

## 阶段 1：AI 应用最小闭环

**目标**: 能用 Python / TypeScript 构建一个最小 AI 应用，而不只是网页对话。

**核心能力**:

- OpenAI / Anthropic API 调用
- Prompt Engineering
- Structured Output
- Tool Calling 基础
- Streaming 输出
- FastAPI / Next.js 基础集成

**推荐项目**: AI 学习资料整理助手 v0

功能：

- 输入一个学习资料链接或仓库名称
- 判断资料类型：理论 / 实操 / 项目 / 面试 / 官方文档
- 输出推荐程度、适合阶段、是否进入主线
- 生成 GitBook Markdown 草稿

**优先资料**:

- OpenAI API Docs
- OpenAI Cookbook
- DeepLearning.ai Prompt Engineering for Developers
- Vercel AI SDK 文档
- Generative AI for Beginners Lesson 04-07、11

**笔记落点**:

- `docs/part1/prompt-engineering.md`
- `docs/part1/openai-api.md`
- `docs/part1/anthropic-api.md`
- `docs/part1/vercel-ai-sdk.md`

---

## 阶段 2：RAG 与资料库工程

**目标**: 构建能处理私有资料的知识库系统。

**核心能力**:

- 文档解析
- Chunking 策略
- Embedding
- 向量数据库
- Hybrid Search
- Rerank
- RAG 评估
- 幻觉和引用控制

**推荐项目**: GitBook 资料问答助手

功能：

- 读取当前 GitBook Markdown 文档
- 建立本地或云端向量索引
- 支持询问“我现在该学什么”
- 回答时引用具体笔记来源
- 记录检索失败案例

**优先资料**:

- LlamaIndex 官方文档
- OpenAI Knowledge Retrieval
- Generative AI for Beginners Lesson 15
- LLM Cookbook RAG 相关章节
- agent-study Ch9 / Ch25 作为概念补充

**笔记落点**:

- `docs/part2/embedding.md`
- `docs/part2/vector-database.md`
- `docs/part2/llamaindex.md`
- `docs/projects/treasure-assistant.md`

---

## 阶段 3：Tool Calling 与工作流

**目标**: 从单次问答升级为多步骤任务执行。

**核心能力**:

- Function / Tool Schema 设计
- 工具选择逻辑
- 工具调用失败处理
- 多工具编排
- 人类确认
- 简单工作流状态
- API 服务化

**推荐项目**: GitHub 仓库评估器

功能：

- 输入 GitHub 仓库地址
- 自动读取 README、目录和示例代码
- 判断它是理论资料、实操教程、项目模板还是源码研究对象
- 输出是否纳入主线，以及推荐阅读章节
- 自动生成 GitBook 资料评估记录

**优先资料**:

- OpenAI Tool Calling / Structured Outputs 文档
- Anthropic Tool Use 文档
- Vercel AI SDK Tool Calling 示例
- agent-study Ch1 / Ch11 / Ch27

**笔记落点**:

- `docs/part3/tool-calling.md`
- `docs/projects/treasure-assistant.md`

---

## 阶段 4：Agent 状态管理与 LangGraph

**目标**: 构建可控、可恢复、可观察的 Agent 工作流。

**核心能力**:

- LangGraph StateGraph
- Node / Edge / Conditional Edge
- Checkpoint / Memory
- Human-in-the-loop
- 中断和恢复
- 多步骤计划执行
- Agent 评估

**推荐项目**: 学习路线规划 Agent

功能：

- 读取 GitBook 中的资料库
- 根据当前时间、背景、目标生成学习计划
- 自动判断哪些资料该看、哪些该跳过
- 遇到不确定选择时向用户确认
- 输出每周计划和学习日志草稿
- 记录每一步工具调用和决策原因

**优先资料**:

- LangGraph 官方文档和 Academy
- OpenAI Agents SDK
- Anthropic Building Effective Agents
- agent-study Ch4 / Ch19 / Ch20

**笔记落点**:

- `docs/part3/langgraph-basics.md`
- `docs/part3/state-management.md`
- `docs/projects/gomoku-commentator.md`

---

## 阶段 5：生产化与工程能力

**目标**: 让 AI / Agent 系统从 demo 变成可上线、可维护的工程。

**核心能力**:

- FastAPI 服务化
- 异步任务和队列
- 数据库存储
- 日志和 tracing
- Evals
- 成本统计
- 权限和审计
- Prompt / Agent 版本管理
- 安全边界和工具沙箱

**推荐项目**: 生产级资料研究 Agent

功能：

- 支持多资料并发分析
- 支持任务状态追踪
- 支持人工审批后写入 GitBook
- 支持失败重试
- 支持评估样例集
- 有前端界面展示 Agent 执行过程

**优先资料**:

- FastAPI 官方文档
- LangSmith / LangGraph Observability
- Anthropic Context Engineering
- 12-Factor Agents
- agent-study Ch18 / Ch24 / Ch30 / Ch36

**笔记落点**:

- `docs/part4/README.md`
- `docs/resources/README.md`

---

## 实战项目顺序

### 项目 1：AI 学习资料整理助手

- **阶段**: 1
- **价值**: 直接服务当前 GitBook 和资料筛选需求
- **技术栈**: Python / OpenAI API / Structured Output / Markdown

### 项目 2：GitBook 资料问答助手

- **阶段**: 2
- **价值**: 建立 RAG 能力，将学习笔记变成可查询知识库
- **技术栈**: Python / LlamaIndex / Vector DB / RAG

### 项目 3：GitHub 仓库评估器

- **阶段**: 3
- **价值**: 训练 Tool Calling、资料分析和结构化报告能力
- **技术栈**: Python / GitHub API / Tool Calling / FastAPI

### 项目 4：学习路线规划 Agent

- **阶段**: 4
- **价值**: 进入 Agent 状态管理和工作流编排
- **技术栈**: LangGraph / OpenAI Agents SDK / RAG / Human-in-the-loop

### 项目 5：五子棋解说 Agent

- **阶段**: 4-5
- **价值**: 兴趣项目，适合验证工具调用、状态管理和前端展示
- **技术栈**: LangGraph / Python / TypeScript / Streaming UI

---

## 学习进度追踪

| 阶段 | 状态 | 目标产出 |
|------|------|----------|
| 阶段 0：路线收敛与资料筛选 | 进行中 | 职业定位、资料分类、学习路线 |
| 阶段 1：AI 应用最小闭环 | 待开始 | AI 学习资料整理助手 v0 |
| 阶段 2：RAG 与资料库工程 | 待开始 | GitBook 资料问答助手 |
| 阶段 3：Tool Calling 与工作流 | 待开始 | GitHub 仓库评估器 |
| 阶段 4：Agent 状态管理与 LangGraph | 待开始 | 学习路线规划 Agent |
| 阶段 5：生产化与工程能力 | 待开始 | 生产级资料研究 Agent |

---

## 讨论记录

### 2026年5月13日

- 初步确定学习路线：快速上手实践，利用 TS 优势
- 学习周期：从 24 周压缩到 4-6 周
- 核心资源：LLM Cookbook + Generative AI for Beginners + Harness 工程指南
- 优先使用 TypeScript 工具：Vercel AI SDK、LangGraph.js

### 2026年5月19日

- 明确不走纯算法/模型训练路线
- 明确不做纯 AI 前端方向
- 将目标调整为 Full-stack AI / Agent Engineer
- 确认 Agent 工程是主攻方向，但需要从 AI 应用、RAG、Tool Calling 逐步进入
- 路线从“按主题学习”调整为“按岗位能力 + 项目产出”推进

---

*最后更新: 2026年5月19日*
