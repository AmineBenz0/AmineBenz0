<h1 align="center">Amine Benzaarit</h1>

<p align="center">
  <b>AI engineer who builds the whole product, not just the model call.</b><br>
  Agentic AI · RAG · Python backends · Rabat, Morocco 🇲🇦
</p>

<p align="center">
  <a href="https://linkedin.com/in/mohamed-amine-benzaarit"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:amine.benzaarit0@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
</p>

---

## About me

I studied Big Data & AI engineering in Rabat (International University of Rabat, with an exchange semester at the University of Ottawa), then joined DXC Technology as an AI engineering intern and stayed on as an AI engineer. Alongside that I have been building my own product since 2025 and took on freelance work in 2026, so I see AI systems from both ends: inside a large production platform, and as the person who has to ship, host and support the whole thing.

I work in Arabic, French and English.

## What I'm building: Rezva

A multi-tenant SaaS that lets small businesses take bookings over **WhatsApp** through a conversational AI agent, with a web dashboard for the business owner. Pre-launch. The code is private, the design is not a secret:

```
Customer on WhatsApp
  └─ webhook ─▶ FastAPI backend ─▶ Redis stream
                                      └─▶ AI turn worker
                                            └─▶ booking agent (bounded tool-calling loop)
                                                  ├─ check_availability   ├─ list_bookings
                                                  ├─ create_booking       ├─ cancel_booking
                                                  └─ reschedule_booking
                                                        └─▶ outbox ─▶ sender worker ─▶ WhatsApp
Business owner ─▶ Next.js dashboard ─▶ API ─▶ PostgreSQL (row-level security per tenant)
```

- **Tenant isolation in the database**, not just in application code: PostgreSQL row-level security, Alembic migrations.
- **Async by design**: messages flow through Redis streams and background workers (AI turns, WhatsApp sending, calendar sync).
- **A simpler agent on purpose**: it started as a complex multi-agent prototype and I rebuilt it as a bounded tool-calling loop with deterministic booking safeguards, multilingual evaluations and Sentry monitoring.
- **Operated like a real service**: Grafana/Prometheus dashboards, runbooks (secret rotation, tenant onboarding, canary rollout of agent changes).

**Stack:** Python · FastAPI · PostgreSQL · Redis · LangChain · Next.js · Docker · Google Calendar API · WhatsApp Business API

## Production AI at DXC Technology

I work on a RAG and agentic-AI platform used by a public-sector client, and on an enterprise assistant for a large multinational. A few things I designed or led (latency numbers are from local A/B tests, not production dashboards):

| What | Result |
|---|---|
| Moved answer-generation orchestration from Celery tasks to **LangGraph** and benchmarked it | **-45.6%** mean first-chunk latency (35.2s → 19.1s, 10 runs per path), now in production |
| Found memory and concurrency bottlenecks, guided async + Redis/Elasticsearch changes | **-69.7%** p95 first-chunk latency (13.6s → 4.1s, 4 virtual users) |
| Hierarchical RAG context enrichment | Document and section summaries plus breadcrumbs added after ChromaDB retrieval, so answers keep the meaning of the source |
| Query routing by complexity | Simple questions skip LLM rewriting and decomposition; complex ones keep the multi-step path |
| Tenant-scoped **MCP** tools | Per-client tool registry (PostgreSQL, Redis sync); the gateway checks allowed tools at execution time |
| Production incident investigation | 40+ incidents on an enterprise assistant traced to root cause (parameter mapping, workflow errors) with Copilot Studio, Power Automate and Azure Application Insights |

## Projects you can open

| Repo | What it is |
|---|---|
| [HelpDesk_Multi_Agent_System](https://github.com/AmineBenz0/HelpDesk_Multi_Agent_System) | LangGraph multi-agent helpdesk: monitors Gmail/Outlook, classifies requests vs incidents, extracts fields and priority, routes tickets, follows up on missing information, stores tickets in Elasticsearch, with a live dashboard. |
| [backend-assistant](https://github.com/AmineBenz0/backend-assistant) | VectorRAG backend pipeline: document processing, ChromaDB vector search, Azure OpenAI embeddings, MinIO storage, Celery workers with Redis, all behind FastAPI and Docker Compose. |

## Client work

A back-office platform for a freelance client that replaced Excel workflows: ledger, stock and payments with an audit trail, JWT auth with roles, PostgreSQL triggers for traceability. FastAPI, React, Supabase/PostgreSQL, GitHub Actions gates and Vercel staging/production releases. (Private, client code.)

## Tools I reach for

| | |
|---|---|
| **Agents & LLMs** | LangGraph, LangChain, MCP, tool calling, Azure OpenAI, evaluation sets |
| **Retrieval** | ChromaDB, Elasticsearch, embeddings, reranking |
| **Backend** | Python, FastAPI, asyncio, PostgreSQL, Redis, Celery, Alembic |
| **Frontend** | React, Next.js |
| **Quality & ops** | Docker, GitHub Actions, pytest, Playwright, Langfuse, Sentry, Grafana |

## Certifications

Claude Certified Architect (Professional) · Claude Certified Developer (Foundations) · AWS Certified AI Practitioner · Microsoft Certified: Azure AI Fundamentals

## Work with me

I'm open to AI and agentic-engineering roles in Morocco or abroad (remote, hybrid or on-site). Email or LinkedIn is the fastest way to reach me.
