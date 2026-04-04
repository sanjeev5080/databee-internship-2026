# Use Case — Data Engineering & DevOps

**Track Lead:** Sanjeev Kumar

---

## Smart Retail Analytics & AI-Powered Recommendation Engine

A retail company operates both online and offline stores. They receive raw data from multiple sources — transactional databases, REST APIs, and flat files — and need an end-to-end data platform to power business reporting, customer intelligence, and an AI-assisted product recommendation system.

---

## Data Sources

| Source | Type | Ingestion Method |
|---|---|---|
| Customer & Orders DB | PostgreSQL (OLTP) | Python + SQLAlchemy |
| Product catalog | REST API (paginated JSON) | Python Requests |
| Store inventory & suppliers | CSV files (daily drops) | Pandas / PySpark |
| User clickstream / behavior | JSON logs | PySpark |

---

## Pipeline Stages

### Stage 1 — Extract (Bronze)
Ingest from all sources into cloud storage (S3 / Azure Blob), partitioned by ingestion date. Raw data stored as-is.

### Stage 2 — Silver (Cleaning & Enrichment)
- Remove nulls, duplicates, invalid records.
- Standardize timestamps and currency.
- Join orders → customers → products.
- Deduplicate using SQL Window Functions (`ROW_NUMBER`).
- Use CTEs for readable transformation logic.

### Stage 3 — Data Modeling
- Design a Star Schema: `fact_orders` + `dim_customer`, `dim_product`, `dim_date`, `dim_store`.
- Load into a cloud warehouse (Snowflake / BigQuery / Redshift).

### Stage 4 — Gold Layer with dbt
- Build dbt models for business metrics: revenue by product, customer lifetime value, customer segments (High/Mid/Low), store performance, inventory health.
- Add dbt tests: `not_null`, `unique`, custom SQL.

### Stage 5 — Scale with PySpark
- Re-implement Silver → Gold transformations in PySpark.
- Handle millions of rows with partitioning and caching.
- Compare Pandas vs PySpark for scale.

### Stage 6 — Orchestration with Airflow
- Daily DAG at 10 AM: extract → silver → gold → dbt run → notify.
- Add retry logic, failure alerts, backfill support, data quality sensor tasks.

### Stage 7 — AI Layer (RAG + Vector DB)
- Embed product descriptions → store in Pinecone or pgvector.
- Build a RAG pipeline for semantic product search and personalized recommendations using purchase history.

### Stage 8 — CI/CD & Production Hardening
- GitHub Actions pipeline: lint → test → staging → prod.
- Environment-based dbt profiles.
- Bash scripts for health checks and backfills.
- Full documentation and architecture diagram.

---

## Implementation Approaches

**Approach 1 — Cloud Native**
```
Python → S3/Azure Blob → Snowflake/BigQuery → dbt → Airflow → pgvector/Pinecone → GitHub Actions
```

**Approach 2 — PySpark Stack**
```
Python + PySpark → Parquet/HDFS → PostgreSQL or Databricks → dbt → Airflow (local) → pgvector → GitHub Actions
```

---

## Notes

- Start with Approach 1 (drag-and-drop tools like ADF / Glue / Lakeflow Designer) to understand concepts with minimal code.
- Move to Approach 2 (pure PySpark) once fundamentals are solid — this is the target skill for data engineers.
- Start small (10 MB datasets), then scale to 10 GB+ to understand where distributed systems shine.
- Use ChatGPT or HackerRank to generate sample data for the use case.
