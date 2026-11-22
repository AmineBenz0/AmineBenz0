<h1 align="center">Amine Benzaarit</h1>

<p align="center">
  <b>I build AI systems that keep working after the demo.</b><br>
  Agentic AI · RAG · Python backends · Rabat, Morocco 🇲🇦
</p>

<p align="center">
  <a href="https://linkedin.com/in/mohamed-amine-benzaarit"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:amine.benzaarit0@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
</p>

I'm an AI Engineer at DXC Technology, working on production RAG and agentic systems. I started in data science and machine learning, then got hooked on what comes after the model works: architecture, reliability, speed, and turning an idea into something people use.

---

## What that looks like in numbers

| <h3>−45.6%</h3> | <h3>−69.7%</h3> |
|:---:|:---:|
| mean first-chunk latency after moving answer generation from Celery to **LangGraph** | p95 first-chunk latency after async and Redis / Elasticsearch changes |

<sub>Latency figures come from local A/B tests, not production dashboards.</sub>

---

## Now building: Rezva

A multi-tenant SaaS where small businesses take bookings over **WhatsApp** through an AI agent. Pre-launch, code private.

What makes it interesting is everything around the model: a queue that survives crashes, one agent turn per conversation, two customers never getting the same slot, and a calendar sync that never blindly retries a write after a crash.

**→ [See the architecture and the problems I hit](https://github.com/AmineBenz0/ai-systems-showcase/tree/main/rezva)**

---

## Selected work

| | |
|---|---|
| **[Rezva architecture](https://github.com/AmineBenz0/ai-systems-showcase/tree/main/rezva)** | System map, message flow, the limitations I hit and how I fixed each, and what is still not built. |
| **[HelpDesk Multi-Agent System](https://github.com/AmineBenz0/HelpDesk_Multi_Agent_System)** | Stateful LangGraph agents that turn a support mailbox into routed tickets. My benchmark of local vs hosted LLMs changed the model choice. |
| **[VectorRAG backend](https://github.com/AmineBenz0/backend-assistant)** | Document processing, ChromaDB search and Azure OpenAI embeddings behind FastAPI, Celery and Docker Compose. |

**Stack:** Python · FastAPI · LangGraph · ChromaDB · Elasticsearch · PostgreSQL · Redis · Next.js · Docker

---

<details>
<summary><b>More production AI work at DXC</b></summary>

<br>

| What | Result |
|---|---|
| Hierarchical RAG context enrichment | Document and section summaries plus breadcrumbs added after retrieval, so answers keep the meaning of the source |
| Adaptive query routing | Simple questions skip LLM rewriting; complex ones keep the multi-step path |
| Tenant-scoped **MCP** tools | Administrators control which tools each client can use, checked at execution time |
| Parallelised orchestration | Parts of the pipeline run in parallel to cut response time |

</details>

<details>
<summary><b>Machine learning background</b></summary>

<br>

- **Prediction pipeline (freelance):** daily-updated XGBoost / Random Forest ensemble, 86.3% accuracy and 0.954 AUC, with time-based validation to limit leakage.
- **Incident resolution time (DXC):** Random Forest on ServiceNow data, MSE 1.69, R² 0.54.
- **Anomaly detection (HTBS):** Splunk and network traffic proof of concept.

[Methods and diagrams →](https://github.com/AmineBenz0/ai-systems-showcase/tree/main/ml-and-data)

</details>

<details>
<summary><b>Certifications (8, all verifiable)</b></summary>

<br>

| Certification | Issuer | Earned | Verify |
|---|---|---|---|
| Claude Certified Architect, Professional | Anthropic | Nov 2026 | [Credly](https://www.credly.com/badges/4fb77570-d89c-4280-8d52-a3e4b21e4bbb/public_url) |
| Claude Certified Developer, Foundations | Anthropic | Sep 2026 | [Credly](https://www.credly.com/badges/2fb9eee4-67c3-4c14-8d80-af7f676c7fac/linked_in_profile) |
| Claude Certified Associate, Foundations | Anthropic | Aug 2026 | [Credly](https://www.credly.com/badges/c3cf3d48-1896-4e1d-a993-428cc2ecbfed/linked_in_profile) |
| Generative AI Leader | Google | Aug 2026 | [Credly](https://www.credly.com/badges/d9763717-157d-476c-89cf-ad67d3db1902/linked_in_profile) |
| AWS Certified AI Practitioner | Amazon Web Services | Aug 2026 | [Credly](https://www.credly.com/badges/b8acfef3-3d26-4c0a-9e76-7005f6a38b06/linked_in_profile) |
| Microsoft Certified: Azure AI Fundamentals | Microsoft | Nov 2025 | [Microsoft Learn](https://learn.microsoft.com/api/credentials/share/en-us/BenzaaritMohamedAmine-6468/7F0ADFD67B2D1969?sharingId) |
| Certificate of Achievement, Data Scientist | 365 Data Science | Nov 2024 | [Certificate](https://learn.365datascience.com/c/d0c7045059) |
| Duolingo English Test | Duolingo | Mar 2024 | [Certificate](https://certs.duolingo.com/723e70128fa554c3a47e598d8f2a2095) |

</details>

<details>
<summary><b>Background</b></summary>

<br>

Engineering degree in Computer Science (Big Data & AI), International University of Rabat, with an exchange semester at the University of Ottawa. Arabic (native), English and French (full professional). Also built a poultry-farm accounting platform as a freelance project.

</details>

---

**Open to AI and agentic-engineering roles** in Morocco or abroad, remote or on-site. Email or LinkedIn is the fastest way to reach me.
