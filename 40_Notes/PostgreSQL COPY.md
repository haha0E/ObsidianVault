---
type: note
area: 数据库
status: seed
created: 2026-09-14
updated: 2026-09-14
by: claude
---
# PostgreSQL COPY

**一句话**：`COPY ... TO STDOUT` 把查询结果以 text/CSV/binary 格式沿客户端连接流式吐给应用，跳过应用层"分批 SELECT + 序列化"的往返；31 万行实测从 40 秒降到 10 秒，且传输速率天然受 TCP 背压约束——数据库控制速率，而不是应用层控制。

## 骨架问题（带着问题学）

- `COPY TO STDOUT` 与 psql 元命令 `\copy` 的本质区别（服务器端执行沿连接发送 vs 客户端落文件）？
- text / csv / binary 三种格式怎么选？（binary "somewhat faster" 但可移植性差、类型严格、不允许 DELIMITER/HEADER 等选项）
- 为什么比应用层分批 SELECT 快：省了哪些序列化/反序列化和往返？`WITH CSV HEADER` 里还能加 `ROW_NUMBER() OVER ()` 这类表达式吗（COPY (SELECT ...) 子查询）？
- 流式传输的速率由谁控制？TCP 滑动窗口如何对 COPY 产生背压？与 R2DBC/Reactor 这类应用层背压是什么关系？
- 反方向：`COPY FROM` 批量导入为什么快？`FREEZE` 性能选项用在哪（初始装载）？
- MySQL 生态的等价物是什么（SELECT INTO OUTFILE / 服务端游标 / 流式游标 SSCursor）？为什么没有直接对等的 TO STDOUT？

## 我的理解（学完后自己写）

- 

## 关联

- [[TCP滑动窗口]] — COPY 流式传输的背压来源
- [[物化视图]] — 让数据库替应用层干活
- [[MOC-数据库]]

## 参考

- [COPY (PostgreSQL 官方文档)](https://www.postgresql.org/docs/current/sql-copy.html) — STDOUT/格式/选项语义
- [Populating a Database (PostgreSQL 官方文档)](https://www.postgresql.org/docs/current/populate.html) — COPY vs INSERT 的批量装载建议
- 来源：群聊讨论 2026-09-11（官方文档已核实；提速数字为群内实测，供参考）
