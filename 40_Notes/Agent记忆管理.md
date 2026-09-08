---
type: note
area: AI工程
status: seed
created: 2026-09-08
updated: 2026-09-08
by: claude
---
# Agent记忆管理

**一句话**：把 agent 的会话/项目记忆持久化下来跨会话复用——轻量做法是项目内 docs 目录 + git；重型做法是独立记忆服务（如 LCM：Markdown 为 source of truth，PostgreSQL 只做索引，按 token 预算检索取回）。

## 骨架问题（带着问题学）

- "项目记忆放项目 docs 进 git"和"独立记忆 MCP 服务"各自适合什么场景？跨机器/跨模型需求如何改变选型？
- LCM 为什么坚持 Markdown 做权威存储、数据库只做索引（可随时重建）？这个架构决策换来什么？
- 记忆写入：存"项目总结"和存"原始会话"有什么区别？什么该记、什么不该记？
- 记忆读取：全量注入上下文 vs 按需检索（关键词 + 模糊 + 向量三路召回 RRF 融合），各自的成本与效果取舍？
- 7x24 长跑 session 的 savePoint 与重启恢复为什么耗时？如何把恢复成本降下来？

## 我的理解（学完后自己写）

- 

## 关联

- [[MCP]] — 记忆服务最常见的暴露形态就是一组 MCP 工具
- [[MOC-AI工程]]

## 参考

- [xiaocqaq/LCM (GitHub)](https://github.com/xiaocqaq/LCM) — 跨模型/跨 agent 会话记忆 MCP 服务
- 来源：群聊讨论 2026-09-03（LCM 项目已核实）
