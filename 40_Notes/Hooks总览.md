---
type: note
area: React
status: seed
created: 2026-09-01
updated: 2026-09-01
by: claude
---
# Hooks总览

**一句话**：Hooks 让函数组件拥有"记忆"和"生命周期"，规则只有两条，但背后是链表实现。

## 骨架问题（带着问题学）

- 两条规则是什么（只在顶层调用 / 只在 React 函数中调用）？**为什么**？违反了会发生什么？
- Hooks 出现之前（class 组件时代），逻辑复用是怎么做的（HOC / render props）？Hooks 解决了什么痛点？
- 自定义 Hook `useXxx` 和普通函数的区别到底是什么？
- 一个组件里 useState 为什么能知道"我是第几个 state"？

## 我的理解（学完后自己写）

- 

## 关联

- [[useState]] / [[useEffect]] — 两个最常用的具体 Hook
- [[渲染机制与虚拟DOM]] — 理解"为什么有这些规则"的底层
