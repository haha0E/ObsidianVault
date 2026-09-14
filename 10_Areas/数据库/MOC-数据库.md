---
type: moc
area: 数据库
status: growing
created: 2026-09-14
updated: 2026-09-14
by: claude
---
# MOC-数据库（内容地图）

> 关系型数据库的使用、schema 设计与性能知识入口。卡片在 `40_Notes/`，骨架卡 = 只有问题和链接，正文等你学完自己填。

## SQL 对象与批量数据

- [[物化视图]] — 存数据的可刷新视图，读性能换新鲜度
- [[PostgreSQL COPY]] — 流式导出，速率交给 TCP 背压

## Schema 设计

- [[半结构化数据存储]] — JSON 列 / EAV / 宽表三条路

## 未开卡（学到再建）

- 索引原理与 EXPLAIN
- 事务隔离级别与锁
- 分区表与海量归档
