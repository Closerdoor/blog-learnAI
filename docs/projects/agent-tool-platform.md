# Agent Tool Platform

> 第二作品：由 QQ 机器人兴趣升级而来的插件化 Agent 工具调用平台。

---

## 项目目标

构建一个多通道、插件化、可权限控制的 Agent 工具平台。

QQ 机器人只是其中一种接入通道，核心价值在于：

```text
消息事件 → AI 路由 → 工具选择 → 插件执行 → 权限控制 → 审计日志
```

## 架构设想

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

## 核心能力

- 插件注册
- 工具 schema
- AI 指令路由
- 权限控制
- 限流
- 审计日志
- 多通道接入
- 第三方 API 集成

## 与 CodePilot Lab 的关系

两个项目可以复用底层架构：

- Tool Registry
- Permission Model
- Audit Log
- Human Approval
- Plugin Sandbox

区别是：

- CodePilot Lab 的工具面向开发：文件、Shell、Git、测试。
- Agent Tool Platform 的工具面向消息和插件：搜图、解析、绘图、热搜、语音等。

## 学习路径关联

- 阶段 3：Tool Calling 与 Tool Registry
- 阶段 5：权限、限流、审计和工程化

