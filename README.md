<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2e1065,50:6d28d9,100:a855f7&height=170&section=header&text=Shorya%20Gupta&fontColor=ffffff&fontSize=44&fontAlignY=36&desc=Backend%20%C2%B7%20Databases%20%C2%B7%20Applied%20GenAI&descAlignY=58&descSize=16&animation=fadeIn" width="100%"/>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=17&duration=2800&pause=900&color=A855F7&background=00000000&center=true&vCenter=true&width=520&lines=Row+locks+against+concurrent+double-assignment;One+rate+limit+across+replicas+via+Redis+%2B+Lua;RAG+that+is+measured%2C+not+asserted;Codeforces+Expert+%C2%B7+2100%2B+problems+solved">
</p>

<p align="center">
  <a href="https://codeforces.com/profile/Shoryagg7"><img src="https://img.shields.io/badge/Codeforces-Expert%201687-1F8ACB?style=for-the-badge&logo=codeforces&logoColor=white"></a>
  <a href="https://leetcode.com/Shoryagg7/"><img src="https://img.shields.io/badge/LeetCode-Knight%202105-FFA116?style=for-the-badge&logo=leetcode&logoColor=white"></a>
  <a href="https://linkedin.com/in/shoryag7"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"></a>
  <a href="https://shoryagg7.github.io/portfolio/"><img src="https://img.shields.io/badge/Portfolio-6D28D9?style=for-the-badge&logo=githubpages&logoColor=white"></a>
  <a href="mailto:shoryag.gupta@gmail.com"><img src="https://img.shields.io/badge/Email-A855F7?style=for-the-badge&logo=gmail&logoColor=white"></a>
</p>

<p align="center"><sub>CSE @ Thapar Institute of Engineering and Technology</sub></p>

I build backend systems and measure them instead of assuming they work. Most of what I find
interesting sits in the failure modes — what breaks under concurrency, what a cache quietly
gets wrong, what an evaluation number doesn't actually prove.

---

## 🛠 Projects

### [DocMind](https://github.com/Shoryagg7/docmind) — Privacy-aware, evaluated agentic RAG over PDFs

Ask questions about your PDFs. A LangGraph agent retrieves from pgvector, grades each chunk
for relevance, rewrites the query and retries when retrieval comes back weak, then answers
with citations. Because the LLM is external, every outbound message passes a local egress
gate that swaps names, emails, phones, PAN and Aadhaar numbers for placeholders and restores
them on this machine — and fails closed if detection errors.

**Measured, not asserted:**

| Metric | Result |
|---|---|
| Retrieval recall@1 / MRR@5 | 19/27 · 0.840 |
| Answer accuracy, privacy on vs off | 30/31 vs 29/31 — no measurable loss (paired sign test, p = 1.0) |
| Cost of the privacy layer | +107 tokens, +0.28 s per question |
| Relevance grading's share of tokens | 72.7% |
| Statement vs its own negation | 0.87 similarity (unrelated text: 0.47) |

The negation result is the one I'd talk about: with (the cache's embedder), a negated
question scores **0.9879** against the original while the paraphrase the cache exists to serve
scores **0.9399**. The case that must be rejected outscores the case that must be accepted, so
no similarity threshold separates them.

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white">
  <img src="https://img.shields.io/badge/PostgreSQL%20%2B%20pgvector-4169E1?style=flat-square&logo=postgresql&logoColor=white">
  <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white">
  <img src="https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square&logo=langchain&logoColor=white">
  <img src="https://img.shields.io/badge/Presidio-6D28D9?style=flat-square">
  <img src="https://img.shields.io/badge/sentence--transformers-A855F7?style=flat-square">
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white">
</p>

---

### [DeliverIQ](https://github.com/Shoryagg7/deliveriq) — Distributed order dispatch API

Assigns incoming delivery orders to available riders across multiple API replicas under
concurrent load. Redis holds the state the replicas share, including a token-bucket rate
limiter run as an atomic Lua script so one limit holds across all of them. Kafka carries
order and dispatch events with consumer groups and at-least-once delivery, and PostgreSQL
transactional locking stops two concurrent requests from assigning the same order.

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white">
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white">
  <img src="https://img.shields.io/badge/SQLAlchemy-D71F00?style=flat-square&logo=sqlalchemy&logoColor=white">
  <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white">
  <img src="https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white">
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white">
  <img src="https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white">
  <img src="https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white">
</p>

---

## ⚙️ Stack

<p align="center">
  <img src="https://skillicons.dev/icons?i=cpp,py,postgres,fastapi,redis,kafka,docker,linux,git,prometheus,grafana&theme=dark&perline=11">
</p>

| | |
|---|---|
| **Languages** | C++ · Python · SQL |
| **Backend** | FastAPI · REST APIs · PostgreSQL · SQLAlchemy · Redis · Kafka |
| **GenAI** | RAG · embeddings · vector search · LangGraph · pgvector · evaluation |
| **Tools** | Git · Docker · Linux · Prometheus · Grafana |

## 🏆 Achievements

- Codeforces **Expert** (1687) · LeetCode **Knight** (2105) · 2100+ problems solved
- **Runner-Up**, SPHINX'24 Hackathon, MNIT Jaipur (2500+ registrations)
- **Runner-Up**, Inter-College Coding Contest, Thapar
- **Merit Scholarship**, Thapar Institute (9.34 AGPA)

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:a855f7,50:6d28d9,100:2e1065&height=110&section=footer" width="100%"/>
