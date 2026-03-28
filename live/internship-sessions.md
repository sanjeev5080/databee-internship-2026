# Databee Internship 2026 — Session Notes

---

## Session 1 — March 21, 2026

**Attendees:** Sanjeev Kumar (mentor), Suhash Raja, Filip Cedermark, Deepika Elangovan, Neha Doda, Kousalya (organizer)

**Agenda:**
1. Introductions (experience, expectations, fun fact)
2. Structure of sessions — discussion
3. Common session plan for all streams

**Notes:**

Session structure agreed:
- Saturday 1-hour sessions (mentors unavailable on weekdays)
- First month: common sessions for all streams covering foundational topics
- 4 streams planned: DA, DE, DevOps/Infra, ML/Analytics

Intern introductions & stream assignments:

- **Suhash Raja** — Major: DE + DevOps. 10 yrs IT (PL/SQL, Splunk, Docker, Terraform, GitHub Actions). Databricks Associate certified.
- **Filip Cedermark** — Major: Data Engineering. Vocational AI/ML school, 17-week internship at Postnode (PySpark/Databricks), consulting bootcamp.
- **Deepika Elangovan** — Major: DE + DevOps. 4 yrs DevOps at Accenture (Azure, CI/CD, Terraform, Kubernetes). Wants to expand into DE.
- **Neha Doda** — Major: DA (primary), interested in DA + DE combo. Power BI, PL-300 certified (Jan 2026), end-to-end BI background.

Key discussion points:
- AI philosophy: build foundational knowledge first, use AI as a companion — not vibe-coding from day one
- AI impact on DA roles discussed (Databricks Genie/AI BI); Neha's DA + DE combo recommended as a strong skillset
- Vinod (mentor) intro not completed — transcript cut off

---

## Session 2 — March 28, 2026

**Attendees:** Sanjeev Kumar (mentor), Vivek (AM), Vinod (AM), Suhash Raja, Filip Cedermark, Deepika Elangovan, Neha Doda, Kousalya (organizer)

**Agenda:**
1. Week check-in — what did you work on? Anything to share?
2. Use cases defined per stream
3. Architectural discussion

**Notes:**

### 1. Week Check-in

*(To be filled during session — what each intern worked on this week, blockers, wins)*

---

### 2. Use Cases Defined per Stream

Each intern now has a defined use case that will be their north star through the internship. These are end-to-end projects that build progressively each month.

**DA — Neha Doda**
- Build an end-to-end BI solution: find a real/messy dataset (Kaggle), clean it in Python, query it in SQL, and build an interactive dashboard in Power BI with KPIs and business storytelling
- Goal: demonstrate the full analyst workflow from raw data → insight → decision

**DE — Filip Cedermark**
- Build an end-to-end data pipeline: ingest data via Python (API or scrape) → land in a cloud data warehouse → transform with dbt → orchestrate with Airflow
- Goal: production-grade pipeline that runs automatically and handles real data

**DE + DevOps — Suhash Raja & Deepika Elangovan**
- DE track: same pipeline as above (Python → Cloud DWH → dbt → Airflow)
- DevOps layer on top: provision the infrastructure with Terraform, containerize components with Docker, and wire it all together with a CI/CD pipeline (GitHub Actions)
- Goal: a fully automated, infrastructure-as-code data platform

---

### 3. Architectural Discussion

Overall architecture the team is building towards — each stream owns a layer:

```
[ Source / Raw Data ]
        |
        v
[ Ingestion — Python (APIs, scraping) ]          ← DE
        |
        v
[ Storage — Cloud Data Warehouse (S3 / Blob) ]   ← DE + DevOps
        |
        v
[ Transform — dbt (SQL-based models) ]            ← DE
        |
        v
[ Orchestration — Apache Airflow ]                ← DE
        |
        v
[ Serve — Power BI / Tableau / Databricks Genie ] ← DA
        |
        v
[ ML Layer — PySpark / MLflow (future) ]          ← ML stream

[ DevOps / Infra layer wrapping everything ]
  → Terraform (provision), Docker (containerize),
    GitHub Actions (CI/CD), Kubernetes (orchestrate)
```

Key architectural decisions discussed:
- Cloud provider: pick one (AWS or Azure) and go deep — don't spread across all three
- dbt sits between storage and serving; it's the transformation engine the DA also needs to understand
- Airflow schedules the whole pipeline — DE owns this but DevOps deploys it
- CI/CD ensures any code change is tested and deployed automatically — no manual deploys

---

## Session 3 — *(upcoming)*

**Attendees:**

**Agenda:**

**Notes:**
