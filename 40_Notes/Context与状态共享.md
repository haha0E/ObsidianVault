---
type: note
area: React
status: seed
created: 2026-09-01
updated: 2026-09-19
by: claude
---
# Context与状态共享

**一句话**：Context 解决"props 一层层传"的问题，但它不是状态管理库——先想清楚是不是真的需要它。

## 骨架问题（带着问题学）

- props drilling 是什么？什么时候值得用 Context 而不是继续传 props？
- Context 值变了，哪些组件会重渲染？怎么避免无关组件陪跑？（提示：拆分 Provider / children 技巧）
- 为什么官方说 Context 主要适合"低频更新的全局数据"（主题、语言、登录态）？
- Context + useReducer 组合与 Redux 的核心差异是什么？

## 我的理解（学完后自己写）

- 

## 关联

- [[Props与State]] — 它解决的问题从这里来
- [[useState]] — 本地状态的对照
