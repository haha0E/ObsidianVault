---
type: note
area: React
status: seed
created: 2026-09-01
updated: 2026-09-19
by: claude
---
# 渲染机制与虚拟DOM

**一句话**：render 只是"算出 UI 应该长什么样"，commit 才碰真实 DOM——两阶段分离是一切性能问题的根源。

## 骨架问题（带着问题学）

- render 和 commit 是什么关系？setState 到屏幕更新之间发生了什么？
- 虚拟 DOM diff 的前提假设是什么（同类型组件、key）？key 用数组下标会出什么问题？
- "重渲染"≠"重绘页面"——为什么 state 变了整个组件函数重跑，页面却不卡？
- React 18 的并发渲染（concurrent）改变了什么？

## 我的理解（学完后自己写）

- 

## 关联

- [[Hooks总览]] — 规则的底层原因
- [[组件与JSX]] — 描述如何变成真实节点
