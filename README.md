<h1 align="center">Amine Benzaarit</h1>

<p align="center">
  <b>AI engineer building reliable AI systems and products.</b><br>
  Agentic AI · RAG · Python backends · Rabat, Morocco 🇲🇦
</p>

<p align="center">
  <a href="https://linkedin.com/in/mohamed-amine-benzaarit"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:amine.benzaarit0@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
</p>

---

## About me

I like building things where AI, software and product meet. I started on the data science and machine learning side, then got more interested in what happens **after the model works**: architecture, APIs, distributed workflows, reliability, performance, and turning an idea into something people can use.

Today I'm an AI Engineer at DXC Technology, working on production AI systems. Outside work I build my own products. I'm drawn to problems where something still has to be figured out: making an AI system cheaper and faster, designing a more reliable architecture, or taking a product from a blank page to something real.

Engineering degree in Computer Science (Big Data & AI) from the International University of Rabat, with an exchange semester at the University of Ottawa. Arabic (native), English and French (full professional).

## What I'm building: Rezva

A multi-tenant SaaS that lets small businesses take bookings over **WhatsApp** through a conversational AI agent, with dashboards for the business owner. Pre-launch; the code is private.

**[Read the architecture write-up →](https://github.com/AmineBenz0/ai-systems-showcase/tree/main/rezva)** It covers the system map, how one message flows end to end, the limitations I hit (double bookings, crashes mid calendar-write, a cache lock that hung requests, and more) and how I fixed each one, plus what is still not built.

```
Customer on WhatsApp
  └─ webhook ─▶ FastAPI ─▶ Redis Streams ─▶ AI turn workers ─▶ booking agent (bounded tool loop)
                                                                      └─▶ outbox ─▶ sender ─▶ WhatsApp
Business owner ─▶ Next.js dashboards ─▶ API ─▶ PostgreSQL (row-level security per tenant)
```

**Stack:** Python · FastAPI · PostgreSQL · Redis Streams · LangGraph · Next.js · Docker · Prometheus / Grafana · Sentry

## Production AI at DXC Technology

I work on a RAG and agentic-AI platform for a public-sector client, and on an enterprise assistant for a large multinational. I've worked on the RAG pipeline end to end: document ingestion, metadata enrichment, context structuring, vector indexing, retrieval, reranking, context assembly and inference. A few things I designed or led (latency numbers are from local A/B tests, not production dashboards):

| What | Result |
|---|---|
| Moved answer-generation orchestration from Celery tasks to **LangGraph** and benchmarked it | **-45.6%** mean first-chunk latency (35.2s → 19.1s, 10 runs per path), now in production |
| Found memory and concurrency bottlenecks, guided async + Redis/Elasticsearch changes | **-69.7%** p95 first-chunk latency (13.6s → 4.1s, 4 virtual users) |
| Hierarchical RAG context enrichment | Document and section summaries plus breadcrumbs added after ChromaDB retrieval, so answers keep the meaning of the source |
| Adaptive query routing | Simple questions skip LLM rewriting and decomposition; complex ones keep the multi-step path |
| Tenant-scoped **MCP** tools | Per-client tool registry (PostgreSQL, Redis sync); the gateway checks allowed tools at execution time |
| Production incident investigation | 40+ incidents on an enterprise assistant traced to root cause (parameter mapping, workflow errors) with Copilot Studio, Power Automate and Azure Application Insights |

## Projects you can open

| Repo | What it is |
|---|---|
| [ai-systems-showcase](https://github.com/AmineBenz0/ai-systems-showcase) | Architecture write-ups with diagrams for systems whose code is private: Rezva, and the helpdesk system below. |
| [HelpDesk_Multi_Agent_System](https://github.com/AmineBenz0/HelpDesk_Multi_Agent_System) | My internship project: stateful LangGraph workflows from secure email ingestion to classification, field extraction, priority (RAG-applied domain rules), follow-ups, ticket creation in Elasticsearch and live monitoring. I also built a benchmark of open-source vs hosted LLMs (quality, latency, resources, function calling) that led the PoC to move from small local models to stronger hosted ones. |
| [backend-assistant](https://github.com/AmineBenz0/backend-assistant) | VectorRAG backend pipeline: document processing, ChromaDB vector search, Azure OpenAI embeddings, MinIO storage, Celery workers with Redis, behind FastAPI and Docker Compose. |

## Earlier work: machine learning and data

Before agents I worked on classic ML, which still shapes how I evaluate AI systems.

| When | What | Outcome |
|---|---|---|
| 2024-25, self-employed | Client projects in gaming, sports analytics and sales forecasting; an automated prediction pipeline with daily data updates | XGBoost / Random Forest ensemble, **86.3% accuracy, 0.954 AUC**, time-based validation to limit leakage |
| Summer 2024, DXC | Predicting IT incident resolution time from ServiceNow data | Random Forest after tuning (RandomizedSearchCV): **MSE 1.69, R² 0.54** (5-fold CV against Linear Regression and SVR) |
| Summer 2023, HTBS | Network monitoring with Bash, tcpdump and Splunk ML Toolkit; near-real-time ingestion about every 10 seconds | Proof of concept surfaced a strong anomaly in a controlled brute-force test |
| Summer 2022 | Information systems internship at Morocco's customs administration | First look at enterprise IT in a large public-sector organisation |

## Client work

A back-office platform for a freelance client that replaced Excel workflows: ledger, stock and payments with an audit trail, JWT auth with roles, PostgreSQL triggers for traceability. FastAPI, React, Supabase/PostgreSQL, GitHub Actions gates and Vercel staging/production releases. (Private, client code.)

## Tools I reach for

| | |
|---|---|
| **Agents & LLMs** | LangGraph, LangChain, MCP, tool calling, Azure OpenAI, LLM benchmarking and evaluation |
| **Retrieval** | ChromaDB, Elasticsearch, embeddings, reranking, adaptive query routing |
| **Backend** | Python, FastAPI, asyncio, PostgreSQL, Redis (Streams), Celery, Alembic |
| **Data & ML** | XGBoost, scikit-learn, feature engineering, time-based validation |
| **Frontend** | React, Next.js |
| **Quality & ops** | Docker, GitHub Actions, pytest, Playwright, Langfuse, Sentry, Splunk, Grafana |

## Certifications

Claude Certified Architect (Professional) · Claude Certified Developer (Foundations) · Microsoft Certified: Azure AI Fundamentals · AWS Certified AI Practitioner · Certificate of achievement, Data Scientist · Duolingo English Test

## Work with me

I'm open to AI and agentic-engineering roles in Morocco or abroad (remote, hybrid or on-site), and always happy to talk with people building interesting things. Email or LinkedIn is the fastest way to reach me.
