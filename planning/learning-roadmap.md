# 学习路线规划

> 当前路线：以 **Full-stack AI / Agent Engineer** 为目标，长期靠拢 **Agentic Coding / AI 软件工程工具**，用短周期计划一步步推进。

---

## 当前状态

- **背景**: 前端工程师，熟悉 TypeScript/JavaScript
- **现实工作**: 目前大量使用 Python
- **目标方向**: 全栈 AI / Agent 工程，长期聚焦 Agentic Coding
- **不走路线**: 纯算法、模型训练、纯 AI 前端
- **核心策略**: 先掌握 AI 应用基础，再进入代码库理解、工具调用、Agent Workflow 和工程化
- **开始时间**: 2026年5月

---

## 职业目标

目标不是“会用 AI”，而是：

> 能把 AI 系统做成可靠产品，并逐步构建面向软件开发流程的 Coding Agent 工具。

更具体的岗位定位：

- Full-stack AI Engineer
- AI Application Engineer
- AI Agent Engineer
- LLM Application Engineer
- Agent Workflow Engineer
- Developer Tools / Agentic Coding Engineer

---

## 路线总览

```text
Python / TS AI 应用基础
        ↓
代码库理解与 RAG / Memory
        ↓
Tool Calling 与 Tool Registry
        ↓
Coding Agent Workflow
        ↓
生产化：评估、观测、安全、部署
        ↓
作品集：CodePilot Lab + Agent Tool Platform
```

---

## 阶段 0：路线收敛与资料筛选

**目标**: 明确方向，避免被大而全资料拖住。

**当前状态**: 进行中

**核心任务**:

- [x] 明确不走纯算法/模型训练路线
- [x] 明确不做纯 AI 前端壳子
- [x] 将目标定位为 Full-stack AI / Agent Engineer
- [x] 将长期方向收敛到 Agentic Coding / AI 软件工程工具
- [x] 将资料分为实操类、理论类、查漏类
- [ ] 建立“暂不学习清单”
- [ ] 持续记录路线决策过程

**产出文档**:

- `planning/career-positioning.md`
- `planning/project-direction.md`
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

**短期练习**: API / Prompt / Structured Output / Tool Calling 最小练习

练习目标：

- 调用一次模型
- 让模型输出稳定 JSON
- 让模型调用一个本地工具
- 读取一个本地文件并总结
- 用 FastAPI 包一层简单接口

**和 CodePilot Lab 的关系**:

- 任务分析需要 Structured Output
- 文件读取需要工具调用
- 后续 plan-edit-test loop 需要稳定的模型调用基础

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

## 阶段 2：代码库理解与 RAG / Memory

**目标**: 让 AI 能理解一个代码项目或资料集合，为 Coding Agent 构建上下文。

**核心能力**:

- 文档解析
- Chunking 策略
- Embedding
- 向量数据库
- Hybrid Search
- Rerank
- RAG 评估
- 幻觉和引用控制
- 代码库文件扫描
- 代码搜索 / 符号搜索

**短期练习**: Codebase Q&A

功能：

- 读取一个小型代码项目
- 建立本地或云端向量索引
- 支持询问“这个函数在哪里”“这个模块做什么”
- 回答时引用具体文件来源
- 记录检索失败案例

**长期项目连接**:

- CodePilot Lab 的代码库检索
- Personal Media Graph 的收藏内容检索

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

## 阶段 3：Tool Calling 与 Tool Registry

**目标**: 从单次问答升级为可控工具调用，并形成可复用的工具注册机制。

**核心能力**:

- Function / Tool Schema 设计
- 工具选择逻辑
- 工具调用失败处理
- 多工具编排
- 人类确认
- 简单工作流状态
- API 服务化
- Tool Registry
- Permission Model
- Audit Log

**短期练习**: Local Dev Agent Tools

功能：

- 封装 `read_file`
- 封装 `list_files`
- 封装 `run_command`
- 封装 `git_diff`
- 对高风险工具加入确认机制

**长期项目连接**:

- CodePilot Lab 的 file / shell / git / test tools
- Agent Tool Platform 的插件系统和工具路由

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

**目标**: 构建可控、可恢复、可观察的 Coding Agent Workflow。

**核心能力**:

- LangGraph StateGraph
- Node / Edge / Conditional Edge
- Checkpoint / Memory
- Human-in-the-loop
- 中断和恢复
- 多步骤计划执行
- Agent 评估

**主项目**: CodePilot Lab v0-v3

功能：

- 扫描代码库结构
- 读取相关文件
- 生成修改计划
- 修改文件并展示 diff
- 运行测试或检查命令
- 根据失败结果继续修复
- 记录每一步工具调用和决策原因

版本：

- v0：代码库读取 + 修改建议
- v1：文件修改 + diff
- v2：运行测试 + 自动修复
- v3：LangGraph 状态流

**优先资料**:

- LangGraph 官方文档和 Academy
- OpenAI Agents SDK
- Anthropic Building Effective Agents
- agent-study Ch4 / Ch19 / Ch20

**笔记落点**:

- `docs/part3/langgraph-basics.md`
- `docs/part3/state-management.md`

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

**推荐项目**: CodePilot Lab v4 + Agent Tool Platform

功能：

- 支持权限控制和工具分级
- 支持任务状态追踪
- 支持人工审批
- 支持失败重试
- 支持评估样例集
- 有前端界面展示 Agent 执行过程和 trace

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

### 项目 1：CodePilot Lab

- **阶段**: 2-5
- **价值**: 主线求职作品，面向 Agentic Coding
- **技术栈**: Python / LangGraph / Tool Calling / Git / Shell / Test Runner

### 项目 2：Agent Tool Platform

- **阶段**: 3-5
- **价值**: 第二作品，由 QQ 机器人兴趣升级为插件化工具平台
- **技术栈**: Python / Tool Registry / Plugin System / Permission / Audit Log

### 项目 3：Personal Media Graph

- **阶段**: 2 起长期积累
- **价值**: 长期兴趣产品，练 RAG、知识图谱、推荐和长期记忆
- **技术栈**: Python / RAG / Knowledge Graph / Recommendation

### 项目 4：AI Web Game Studio

- **阶段**: 兴趣实验
- **价值**: 保留为个人兴趣，不纳入当前职业主线
- **技术栈**: TypeScript / Web Game / Playwright

### 项目 5：学习辅助工具

- **阶段**: 按需
- **价值**: 服务学习过程，不作为求职作品主线
- **例子**: GitBook 资料问答、学习路线规划、资料整理脚本

---

## 学习进度追踪

| 阶段 | 状态 | 目标产出 |
|------|------|----------|
| 阶段 0：路线收敛与资料筛选 | 进行中 | 职业定位、资料分类、学习路线 |
| 阶段 1：AI 应用最小闭环 | 待开始 | API / JSON / Tool Calling 小练习 |
| 阶段 2：代码库理解与 RAG / Memory | 待开始 | Codebase Q&A |
| 阶段 3：Tool Calling 与 Tool Registry | 待开始 | Local Dev Agent Tools |
| 阶段 4：Agent 状态管理与 LangGraph | 待开始 | CodePilot Lab v0-v3 |
| 阶段 5：生产化与工程能力 | 待开始 | CodePilot Lab v4 + Agent Tool Platform |

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
- 进一步将长期方向收敛到 Agentic Coding / AI 软件工程工具
- 确认主作品为 CodePilot Lab，副作品为 Agent Tool Platform，长期兴趣产品为 Personal Media Graph
- 确认后续采用短周期学习：用户完成一段学习后反馈，Codex 整理笔记、查漏补缺并制定下一段计划

---

*最后更新: 2026年5月19日*
