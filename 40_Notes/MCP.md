---
type: note
area: AI工程
status: seed
created: 2026-09-08
updated: 2026-09-08
by: claude
---
# MCP

**一句话**：Model Context Protocol，agent 与工具/数据源之间的开放标准协议；服务端声明 `listChanged` 能力后，可以在运行时增删工具并发通知让客户端刷新工具列表——这就是 tool"热更新"的协议基础。

## 骨架问题（带着问题学）

- `tools/list`、`tools/call`、`notifications/tools/list_changed` 三者的交互流程是什么？客户端收到通知后该做什么？
- 为什么"每轮全量组装 tool 列表、把禁用项剔除再发给模型"不影响上下文质量？这和 tool 热更新是什么关系？
- tool 本体要提前开发写死，那"可插拔"指的到底是哪一层（注册？启用？权限）？配置中心拉取 + 热加载如何落地？
- 7x24 长跑 agent 的会话状态放哪（如 Redis）？和 MCP 调用本身的无状态性怎么配合？
- MCP 相比直接写 function calling，换来什么（生态、解耦），付出什么（一层抽象、调试复杂度）？

## 我的理解（学完后自己写）

- 

## 关联

- [[Agent记忆管理]] — 长跑 agent 的另一半：状态与记忆持久化
- [[MOC-AI工程]]

## 参考

- [MCP 规范 — Tools](https://modelcontextprotocol.io/specification/2024-11-05/server/tools)
- 来源：群聊讨论 2026-09-02（listChanged 通知机制已核实）
