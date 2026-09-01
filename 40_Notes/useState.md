---
type: note
area: React
status: seed
created: 2026-09-01
updated: 2026-09-01
by: claude
---
# useState

**一句话**：给函数组件一个"记事本"，改它会触发重渲染。

## 骨架问题（带着问题学）

- `const [n, setN] = useState(0)` 里，每次渲染 `n` 是同一个变量吗？
- 函数式更新 `setN(prev => prev + 1)` 和 `setN(n + 1)` 的区别？什么时候必须用前者？
- 传入对象 state，`setObj({x: 1})` 会保留其他字段吗？（对比 class 时代的 setState）
- 初始值传函数 `useState(() => expensive())` 有什么用？
- 改 state 后读 `n`，为什么拿到的是旧值？

## 我的理解（学完后自己写）

- 

## 关联

- [[Props与State]] — 上层概念
- [[Hooks总览]] — 规则背景
