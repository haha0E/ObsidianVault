---
type: note
area: 网络
status: seed
created: 2026-09-14
updated: 2026-09-14
by: claude
---
# TCP滑动窗口

**一句话**：TCP 的流控由接收方主导——通过头部 Window 字段通告自己还能收多少字节（RCV.WND），发送方被限制在 SND.UNA ~ SND.UNA+SND.WND 内发送；窗口归零即"刹车"，应用取走数据后窗口更新、窗口向右"滑动"恢复发送——这就是应用层能"免费"获得背压的底层原因。

## 骨架问题（带着问题学）

- 发送窗口为什么锚定在 SND.UNA（最老未确认序号）？累积 ACK 如何让窗口"滑动"出新的可发送空间（RFC 9293 Figure 3 的四区划分）？
- 零窗口时发送方还能发什么（零长度探测段）？窗口更新（window update）依赖接收方应用消费缓冲，这如何解释"慢消费端自动拖慢发送端"？
- 滑动窗口（流控）与拥塞控制（cwnd）是两套独立机制——它们如何同时作用于有效发送速率？
- 接收方窗口通告 16 位为何不够用？窗口缩放选项（RFC 7323）怎么扩展？
- 应用层背压（如数据库 COPY 流式导出、Reactor/R2DBC 的 request(n)）与 TCP 流控是什么关系——哪一层在"借用"哪一层的背压？

## 我的理解（学完后自己写）

- 

## 关联

- [[PostgreSQL COPY]] — 背压的典型受益者
- [[MOC-网络]]

## 参考

- [RFC 9293 — Transmission Control Protocol (官方规范)](https://www.rfc-editor.org/rfc/rfc9293.html) — RCV.WND/SND.WND 流控、零窗口行为、SND.WL1/WL2 窗口更新
- 来源：群聊讨论 2026-09-11（RFC 9293 已核实）
