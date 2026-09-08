---
type: note
area: AI工程
status: seed
created: 2026-09-08
updated: 2026-09-08
by: claude
---
# OCR选型

**一句话**：通用文字识别选 PaddleOCR（轻量、中文友好、工业部署成熟），PDF→Markdown 结构化解析选 MinerU（内嵌 PaddleOCR 模型的文档解析引擎），桌面轻量场景可用 Umi-OCR——先分清"识别"和"文档解析"是两件事。

## 骨架问题（带着问题学）

- PaddleOCR 与 MinerU 的定位差异是什么？为什么"PDF 转 Markdown"不等于"OCR"？
- 经典 PP-OCR 系列和 PaddleOCR-VL 系列分别适合什么场景？
- 证照类识别（身份证、手写签名）除了引擎，还需要哪些后处理（字段结构化）与合规考量？
- MinerU 怎么配置强制走 OCR？什么时候该混用商业 OCR API？
- 选型时除了准确率，还要评估哪些：部署形态（本地/服务）、速度（tps）、并发限制、许可证？

## 我的理解（学完后自己写）

- 

## 关联

- [[MOC-AI工程]]

## 参考

- [PaddleOCR (GitHub)](https://github.com/PaddlePaddle/PaddleOCR)
- [MinerU (GitHub)](https://github.com/opendatalab/MinerU)
- [Umi-OCR (GitHub)](https://github.com/hiroi-sora/Umi-OCR)
- 来源：群聊讨论 2026-09-01（项目定位已核实）
