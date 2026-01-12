# 🏢 Doc-Agent Architecture
> 基于 Markdown 文档深度解析的企业级问答 Agent 架构演进实录

---

## 🗺️ 技术矩阵 (Architecture Navigation)

| 核心组件 | 技术实现说明 (Status Quo) | 深度思考与改动日志 (Deep Dive) |
| :--- | :--- | :--- |
| **1. 记忆管理 (Memory)** | 动态 Token 滑动窗口过滤 | [从固定轮数到信息熵管理的演进](./docs/memory/evolution.md) |
| **2. 查询优化 (Query)** | MD 标题级语义检索优化 | [如何利用 md 结构提升召回率](./docs/query/evolution.md) |
| **3. 文档解析 (Parser)** | 标题树状结构化提取 | [解决 md 嵌套列表的解析痛点](./docs/parser/evolution.md) |

---

## 🎯 项目核心价值
1. **结构化认知**：不只是 RAG，而是通过识别 md 的 `#` 标题层级建立知识索引。
2. **决策可追溯**：通过 `evolution.md` 记录每一次技术路线的更迭。
