# 项目方向与作品集规划

> 当前结论：长期靠拢 **Agentic Coding / AI 软件工程工具**，主作品为 CodePilot Lab；兴趣项目保留，但不阻塞主线学习。

---

## 长期北极星

长期方向：

> 做能帮助人和 AI 一起生产软件的系统。

更具体地说，是面向软件开发流程的 Agent 工程：

- 代码库理解
- 任务拆解
- 文件读写
- Shell / Git / Test Runner 工具调用
- 自动修复
- Diff 审查
- 人类审批
- 执行日志和可观测性
- 沙箱和权限控制

这个方向对齐 Claude Code、Codex、Cursor、Copilot Coding Agent、Devin、OpenHands 等产品背后的能力。

---

## 主作品：CodePilot Lab

### 定位

CodePilot Lab 是一个本地 Coding Agent Harness，用来研究和实现 Claude Code / Codex 类工具的核心工作流。

它不是聊天机器人，而是一个能围绕代码库完成任务的 Agent 系统。

### 核心能力

- 扫描代码库结构
- 读取相关文件
- 制定修改计划
- 调用文件工具修改代码
- 运行测试或检查命令
- 根据错误继续修复
- 生成 Git Diff
- 请求人工确认
- 记录执行轨迹

### 版本规划

```text
v0：代码库读取 + 修改建议
v1：文件修改 + diff
v2：运行测试 + 自动修复
v3：LangGraph 状态流
v4：权限控制 + trace + checkpoint
```

### 能力映射

- AI 应用基础：任务理解、结构化输出
- RAG / Memory：代码库检索、上下文构建
- Tool Calling：file、shell、git、test tools
- Agent Workflow：plan-edit-test-fix loop
- 生产化：权限、审计、日志、回滚、评估

### 求职价值

CodePilot Lab 用来证明：

- 能理解 Agentic Coding 的系统架构
- 能把 LLM 接入真实开发工具链
- 能设计工具调用和权限边界
- 能处理测试反馈和自动修复
- 能做可控、可观察、可恢复的 Agent 工作流

---

## 副作品：Agent Tool Platform

### 来源

来自 QQ 机器人兴趣方向，但不定位成“娱乐机器人插件合集”。

更好的定位是：

> 一个多通道、插件化、可权限控制的 Agent 工具调用平台。

### 架构方向

```text
Agent Tool Platform
├── Channel Layer
│   ├── CLI
│   ├── Web
│   └── QQ Bot
├── Plugin System
│   ├── 搜图插件
│   ├── 视频解析插件
│   ├── 热搜插件
│   ├── 表情包插件
│   └── 绘图插件
├── Tool Registry
├── Permission System
├── Rate Limit
├── Audit Log
└── AI Command Router
```

### 学习价值

- Tool Registry
- 插件系统
- 事件驱动
- 多工具编排
- 权限控制
- 限流和审计
- 第三方平台接入

### 与 CodePilot Lab 的关系

两者共用很多底层能力：

- Tool Registry
- Permission Model
- Audit Log
- Human Approval
- Plugin Sandbox

因此它适合作为第二作品，不抢主线。

---

## 长期兴趣产品：Personal Media Graph

### 来源

来自个人收藏馆方向：

- 电影
- 动漫
- 游戏
- 音乐
- 书籍
- 评论
- 笔记
- 衍生信息

### 它不只是收藏列表

Personal Media Graph 的核心是：

> 围绕个人文化内容的知识图谱 + 语义检索 + 推荐系统。

例如，一个作品可以连接：

```text
作品 → 人物 → 公司 → 音乐 → 评论 → 标签 → 我的笔记 → 相似作品
```

### 能力方向

- 多源数据管理
- RAG
- Knowledge Graph
- 语义搜索
- 个性化推荐
- 长期记忆
- 可解释推荐

### 适合的位置

它适合作为长期兴趣产品，不作为第一求职主线。

原因：

- 对个人长期有价值
- 能练 RAG、图谱和推荐
- 但和 Agentic Coding 的求职主线相比，优先级更低

---

## 兴趣实验：AI Web Game Studio

Web 游戏站点仍然保留为兴趣方向，但不纳入当前职业主线。

后续如果要和 Agentic Coding 结合，可以升级为：

> 用 Coding Agent 生成、测试和修复 Web 小游戏的平台。

当前先不投入主线精力。

---

## 项目优先级

| 优先级 | 项目 | 定位 |
|------|------|------|
| S | CodePilot Lab | 主线求职作品，Agentic Coding |
| A | Agent Tool Platform | 第二作品，插件化工具平台 |
| B | Personal Media Graph | 长期兴趣产品，RAG / 图谱 / 推荐 |
| C | AI Web Game Studio | 兴趣实验，不进入当前主线 |

---

## 学习协作方式

后续学习采用短周期迭代：

1. Codex 制定一小段学习计划。
2. 用户按自己的时间完成学习和练习。
3. 用户反馈学习内容、问题和代码结果。
4. Codex 帮忙整理笔记、查漏补缺、更新 GitBook。
5. Codex 根据完成情况制定下一段计划。

原则：

- 不制定过远计划。
- 每次只推进一个小目标。
- 学习内容要能服务长期主线。
- 兴趣项目不阻塞主线学习。

