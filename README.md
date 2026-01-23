
# 🏢 Doc-Agent Architecture

> Enterprise-grade RAG Agent architecture evolved for deep Markdown document analysis.

## 🗺️ Architecture Navigation

| Core Component | 💡 Status Quo | 🔄 ADR / Evolution Deep Dive |
| --- | --- | --- |
| **1. Memory Management** | [Dynamic Token Window & Semantic Compression](./docs/memory/index.md) | [From "Keep All" to "Token Pruning"](./docs/memory/evolution.md) |
| **2. Document Parsing** | [Structure-Aware Markdown Chunking](./docs/parser/index.md) | [From "Fixed-Size" to "Structure-Aware"](./docs/parser/evolution.md) |
| **3. Reasoning Engine** | [Multi-modal ReAct Engine & Hybrid Planning](./docs/react/index.md) | [From "General Search" to "High-Precision Loop"](./docs/react/evolution.md) |

---

## 🎯 Core Implementation

| Module | Key Features | Source |
| --- | --- | --- |
| **ReAct Engine** | **Reasoning Loop**: Thought-Action-Observation cycle, supporting auto-parsing and streaming termination. | `react_core.py` |
| **Dynamic Memory** | **Token Calculus**: Real-time window management using **System Anchor Protection** and **Far-field Semantic Compression**. | `memory_core.py` |
| **Structure-Aware Chunker** | **Syntax Sensitivity**: Hierarchy-based splitting with **Breadcrumb Path Inheritance** and code block protection. | `chunker_core.py` |
| **Task Executor** | **Secure Orchestration**: Hybrid planning (Keyword + LLM) with RBAC tool checks and fault-tolerant retries. | `executor_core.py` |

---

### 🌟 Key Highlights

* **Intelligent Context**: Dynamic Token window strategy maintains near-field conversational fluency while preventing context overflow via far-field semantic summarization.
* **Semantic Integrity**: Structure-aware chunking prevents code/table truncation and injects full breadcrumb paths into every chunk for global context awareness.
* **Reliable Reasoning**: The ReAct loop combined with an execution sandbox minimizes hallucinations and ensures secure, transparent tool orchestration.
