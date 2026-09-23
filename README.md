<h1 align="center">Shorya Gupta</h1>
<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=18&duration=3000&pause=800&center=true&vCenter=true&width=460&lines=Backend+engineering;Databases+and+distributed+systems;Applied+GenAI+with+real+evaluation">
</p>
<p align="center">
  Backend · Databases · Applied GenAI &nbsp;|&nbsp; CSE @ Thapar Institute
</p>

<p align="center">
  <a href="https://codeforces.com/profile/Shoryagg7"><img src="https://img.shields.io/badge/Codeforces-Expert%201687-1F8ACB?style=flat-square&logo=codeforces&logoColor=white"></a>
  <a href="https://leetcode.com/Shoryagg7/"><img src="https://img.shields.io/badge/LeetCode-Knight%202105-FFA116?style=flat-square&logo=leetcode&logoColor=white"></a>
  <a href="https://linkedin.com/in/shoryag7"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white"></a>
  <a href="https://shoryagg7.github.io/portfolio/"><img src="https://img.shields.io/badge/Portfolio-000?style=flat-square&logo=githubpages&logoColor=white"></a>
</p>

I build backend systems and measure them instead of assuming they work. Most of what I find
interesting sits in the failure modes — what breaks under concurrency, what a cache quietly
gets wrong, what an evaluation number doesn't actually prove.

---

## Projects

### [DocMind](https://github.com/Shoryagg7/docmind) — Privacy-aware, evaluated agentic RAG over PDFs

Ask questions about your PDFs. A LangGraph agent retrieves from pgvector, grades each chunk
for relevance, rewrites the query and retries when retrieval comes back weak, then answers
with citations. Because the LLM is external, every outbound message passes a local egress
gate that swaps names, emails, phones, PAN and Aadhaar numbers for placeholders and restores
them on this machine — and fails closed if detection errors.

Measured, not asserted:

| | |
|---|---|
| Retrieval recall@1 / MRR@5 | 19/27 · 0.840 |
| Answer accuracy, privacy on vs off | 30/31 vs 29/31 (paired sign test p = 1.000) |
| Cost of the privacy layer | +107 tokens, +0.28 s per question |
| Relevance grading's share of tokens | 72.7% |
| A statement vs its own negation | 0.87 similarity (vs 0.47 for unrelated text) |

The negation result is the one I'd talk about: a negated question scores **0.9879** against the
original while the paraphrase the cache exists to serve scores **0.9399** — the case that must
be rejected outscores the case that must be accepted, so no similarity threshold separates them.

`Python` `FastAPI` `PostgreSQL + pgvector` `Redis` `LangGraph` `Presidio` `sentence-transformers` `Docker`

---

### [DeliverIQ](https://github.com/Shoryagg7/deliveriq) — Distributed order dispatch API

Assigns incoming delivery orders to available riders across multiple API replicas under
concurrent load. Redis holds the state the replicas share, including a token-bucket rate
limiter run as an atomic Lua script so one limit holds across all of them. Kafka carries
order and dispatch events with consumer groups and at-least-once delivery, and PostgreSQL
transactional locking stops two concurrent requests from assigning the same order.

`Python` `FastAPI` `PostgreSQL` `SQLAlchemy` `Redis` `Kafka` `Docker` `Prometheus` `Grafana`

---

## Skills

**Languages** C++ · Python · SQL
**Backend** FastAPI · REST APIs · PostgreSQL · SQLAlchemy · Redis · Kafka
**GenAI** RAG · embeddings · vector search · LangGraph · pgvector · evaluation
**Tools** Git · Docker · Linux · Prometheus · Grafana

## Achievements

Codeforces Expert (1687) · LeetCode Knight (2105) · Runner-Up SPHINX'24, MNIT Jaipur ·
Runner-Up Inter-College Coding Contest, Thapar · Merit Scholarship, Thapar

📧 shoryag.gupta@gmail.com
