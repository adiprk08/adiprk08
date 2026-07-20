# Adithya Prakash Namboodiri

Software engineering student at the University of Sydney. I work on retrieval systems and applied ML — mostly the engineering side of getting models and LLM systems into production, rather than the modelling alone.

**Currently:** going deeper on hybrid retrieval — chunking strategies, dense vs sparse tradeoffs, and rank fusion.

**Looking for:** ML, data, and software engineering internships in Sydney or remote.

---

### Projects

**Repo Assistant** — Retrieval-augmented assistant for understanding unfamiliar codebases.

Point it at a GitHub repository and ask questions in natural language. Rather than doing keyword search or naive chunk-and-embed, it builds a structured model of the codebase: a symbol-level index, a cross-file code graph, and hierarchical summaries.

- AST-aware chunking via tree-sitter, so chunks respect function and class boundaries
- Hybrid retrieval — dense + sparse, fused with reciprocal rank fusion, then cross-encoder reranked
- Symbol-level code graph in Postgres for cross-file traversal
- Router that chooses between a fast RAG path and a budgeted agentic loop
- Every answer cites `file:line` at a pinned commit, verified against the index before it's shown
- Exposes read-only code-navigation tools over MCP for use inside Claude Desktop and Cursor

*Python 3.12 · FastAPI · Qdrant · Postgres · tree-sitter · Redis · Docker · Anthropic API*

`Going public September 2026`

---

**Driver Drowsiness Detection** — Deep learning pipeline detecting driver drowsiness from face imagery, with a real-time webcam demo and staged alarm.

Group project for ENGG2112 (4 members). Two experiments: an architecture comparison on a single dataset, then combined training across two datasets to close the cabin-camera-to-webcam distribution gap.

- Five architectures compared — from-scratch CNN, AlexNet and MobileNetV2 transfer learning, and a two-stream eye/face fusion model
- Subject-disjoint splits throughout, so no subject appears in both train and test
- Best combined macro-F1 **0.813**, ROC-AUC **0.892**; threshold calibration lifts drowsy recall to **0.956** for the safety target
- The most interesting result: MobileNetV2 won on held-out metrics but its ImageNet-pretrained extractor saturated at 0.1–0.4 on the target webcam regardless of alertness state. The weaker-scoring BaselineCNN produced well-separated real-time outputs, so it was deployed instead. Offline metrics alone aren't deployment readiness.
- Live demo: MediaPipe face landmarking → face crop → per-frame inference → 30-frame rolling smoother → hysteresis → flash at 2.5s, siren at 4s

*PyTorch · MediaPipe · OpenCV · SQLite · NumPy*

`Going public August 2026`

---

### Stack

**Languages** Python · SQL · JavaScript
**ML** PyTorch · Transformers · scikit-learn · NumPy · OpenCV
**Retrieval** Qdrant · BM25 · cross-encoder reranking · tree-sitter
**Backend** FastAPI · Postgres · Redis · Docker
**Tooling** Git · GitHub Actions · uv

---

[LinkedIn](https://www.linkedin.com/in/adithya-namboodiri/) · [adithyaprakash0808@gmail.com](mailto:adithyaprakash0808@gmail.com)
