# Shawn Ijaz — Senior Data Engineer

<div align="center">

[![Email](https://img.shields.io/badge/Email-shawnijaz0%40gmail.com-blue?style=for-the-badge&logo=gmail&logoColor=white)](mailto:shawnijaz0@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-shawn--ijaz-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/shawn-ijaz-420014440)
[![GitHub](https://img.shields.io/badge/GitHub-shane--ejaz-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ijaro)
[![Location](https://img.shields.io/badge/Location-Albany%2C%20NY-gray?style=for-the-badge&logo=googlemaps&logoColor=white)](#)
[![Python](https://img.shields.io/badge/Python-3.9%20%7C%203.10%20%7C%203.11-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)

<p align="center">
  <b>Batch & Streaming ETL/ELT • Snowflake & Databricks • Apache Spark & Airflow • dbt Core • Real-Time CDC & ClickHouse • Enterprise RAG Ingestion</b>
</p>

</div>

---

## Professional Summary

Senior Data Engineer with **7+ years of experience** architecting high-throughput batch and streaming ETL/ELT pipelines across AWS and Azure cloud ecosystems. Deep specialization in modern Lakehouse architectures, dimensional modeling (Kimball SCD Type 1/2), orchestration, and data platform cost optimization.

- **Warehouse & Lakehouse**: Snowflake, Databricks, Delta Lake, ClickHouse, Apache Iceberg, Amazon Redshift, Google BigQuery, Azure Synapse.
- **Big Data & Streaming**: Apache Spark (PySpark, Structured Streaming), Delta Live Tables, Apache Kafka, Debezium CDC, AWS Kinesis.
- **Orchestration & Transformation**: dbt (Core/Cloud), Apache Airflow (180+ production DAGs), Azure Data Factory, AWS Glue.
- **AI & ML Workloads**: Production RAG ingestion & embedding pipelines, `pgvector`, MLflow feature engineering, LLM token & cost attribution (Amazon Bedrock & OpenAI).
- **Certifications**: AWS Certified Data Engineer (DEA-C01), Databricks Certified Data Engineer Professional, SnowPro Core, Microsoft Azure Data Engineer Associate (DP-203), Databricks Certified Generative AI Engineer.

---

## Flagship Production Repositories

| Repository | Organization & Era | Core Architecture & Technology Stack | Status |
| :--- | :--- | :--- | :---: |
| [**`enterprise-rag-data-pipeline`**](https://github.com/ijaro/enterprise-rag-data-pipeline) | **Solgenci**<br>*(2024 – Present)* | **Production RAG Ingestion & LLM Cost Attribution**<br>• Document Chunking & Metadata Extraction Engine<br>• Vector Store Embedding Sync (`pgvector` / Vector Store)<br>• Bedrock & OpenAI Per-Team Token & Cost Telemetry<br>• Airflow DAG Nightly Warehouse Retrieval Refresh | **Passing Tests (100%)** |
| [**`lakehouse-cdc-streaming-platform`**](https://github.com/ijaro/lakehouse-cdc-streaming-platform) | **Solgenci**<br>*(2023 – 2024)* | **Real-Time CDC, ClickHouse OLAP & dbt Lakehouse**<br>• Debezium + Kafka + Delta Lake CDC Replication (<10m latency)<br>• ClickHouse Real-Time Sub-Second OLAP Engine<br>• 300+ Stored Procedure to dbt ELT Migration<br>• Great Expectations Ingestion Gates & PII Masking | **Passing Tests (100%)** |
| [**`aws-emr-spark-lakehouse`**](https://github.com/ijaro/aws-emr-spark-lakehouse) | **Reno Techs**<br>*(2020 – 2022)* | **High-Scale PySpark on EMR & Redshift Star Schema**<br>• 800 GB/day PySpark Compaction & Partition Pruning Engine<br>• Redshift Kimball Star Schema with SCD Type 2 Dimensioning<br>• Kinesis & Lambda Clickstream Pipeline (5M events/day)<br>• Automated Source-to-Warehouse Reconciliation & Alerting | **Passing Tests (100%)** |
| [**`azure-synapse-dw-pipeline`**](https://github.com/ijaro/azure-synapse-dw-pipeline) | **Letsremotify**<br>*(2018 – 2020)* | **Enterprise DW & Azure Synapse Migration**<br>• Incremental Change-Tracking Extract Engine (Python/T-SQL)<br>• T-SQL Execution Plan Tuning & Table Partitioning Maintenance<br>• Azure Data Factory & Azure Synapse Analytics Workloads<br>• Hive & Spark Order History Analytics on Hadoop | **Passing Tests (100%)** |

---

## Technical Deep-Dives

### 1. Enterprise RAG Ingestion & Token Attribution (`enterprise-rag-data-pipeline`)
*Solgenci (Delaware, US) | 2024 – Present*
- **Problem**: Support and sales teams required accurate, low-latency document search over product docs and internal CRM notes without unmonitored LLM spend or stale embeddings.
- **Implementation**:
  - Engineered modular Python chunking pipelines with sliding-window token overlap and metadata preservation.
  - Implemented vector ingestion with batch upserts into `pgvector`, synchronized via a nightly Apache Airflow DAG.
  - Built an LLM telemetry layer tracking prompt/completion tokens across Amazon Bedrock and OpenAI APIs, attributing exact operational costs by team ID and business unit.

### 2. Real-Time CDC & Lakehouse Platform (`lakehouse-cdc-streaming-platform`)
*Solgenci (Delaware, US) | 2023 – 2024*
- **Problem**: 40 operational Postgres database tables suffered from 24-hour sync latencies and slow stored-procedure ETL running over 6.5 hours.
- **Implementation**:
  - Implemented change data capture (CDC) using Debezium, Kafka, and Delta Lake, dropping sync latency from 24 hours to under 10 minutes.
  - Deployed ClickHouse as a real-time analytics acceleration layer, enabling sub-second analytical queries across billions of event rows without straining Snowflake compute warehouses.
  - Migrated 300+ legacy stored procedures to modular, tested dbt models, slashing batch windows from 6.5 hours to 1 hour 50 minutes.
  - Integrated Great Expectations validation gates at ingestion boundaries and enforced dynamic column-level PII masking in Snowflake.

### 3. AWS EMR PySpark Lakehouse & Dimensional Warehouse (`aws-emr-spark-lakehouse`)
*Reno Techs (Nevada, US) | 2020 – 2022*
- **Problem**: Disparate ingestion from 15 source systems (Salesforce, REST APIs, SFTP, MySQL) resulted in uncoordinated data lakes and sluggish Redshift reporting queries (>40s).
- **Implementation**:
  - Architected an AWS S3 data lake with AWS Glue Data Catalog and Athena, processing 800 GB/day using PySpark on Amazon EMR.
  - Applied aggressive partition pruning and Parquet file compaction, reducing Spark execution times by ~50%.
  - Designed a high-performance Kimball Star Schema in Redshift featuring SCD Type 2 tracking for customer and product dimensions, tuning distribution/sort keys to drop dashboard load times to <5 seconds.
  - Built a near-real-time streaming clickstream ingestion pipeline with AWS Kinesis and Lambda handling 5M events daily.

### 4. Enterprise DW & Azure Synapse Migration (`azure-synapse-dw-pipeline`)
*Letsremotify (New Jersey, US) | 2018 – 2020*
- **Problem**: On-premise SQL Server reporting hardware was bottlenecked by monolithic full-table nightly extracts and long-running T-SQL queries.
- **Implementation**:
  - Re-architected nightly batch ingestion into incremental extracts powered by SQL Server change-tracking columns, sharply cutting batch load volumes.
  - Tuned execution plans, rebuilt clustered columnstore indexes, and implemented table partitioning, cutting query times from 3 hours to 45 minutes.
  - Migrated legacy reporting infrastructure to Azure Data Factory and Azure Synapse Analytics (Azure SQL DW).
  - Built scheduled, parameterized analytical reporting workflows replacing manual spreadsheets.

---

## Technical Skills & Tooling Matrix

```text
├── Languages:             Python (Pandas, PySpark, FastAPI), SQL, T-SQL, PL/SQL, Scala, Bash
├── Cloud Ecosystems:      AWS (S3, EMR, Athena, Redshift, Glue, Lambda, Kinesis, IAM, EKS)
│                          Azure (ADLS Gen2, Databricks, Synapse Analytics, Data Factory)
│                          GCP (BigQuery, Cloud Composer)
├── Lakehouse & Storage:   Snowflake, Databricks, Delta Lake, Apache Iceberg, ClickHouse
├── Streaming & CDC:       Apache Kafka, Debezium, AWS Kinesis, Delta Live Tables
├── Orchestration & ELT:   Apache Airflow, dbt (Core/Cloud), Databricks Workflows, Dagster
├── Quality & Governance:  Great Expectations, dbt tests, Snowflake RBAC, Dynamic Data Masking
├── AI Data Engineering:   RAG Pipelines, pgvector, Vector Indexing, Bedrock/OpenAI APIs, MLflow
└── DevOps & CI/CD:        Docker, Kubernetes, Terraform, GitHub Actions, Linux
```

---

## Education & Professional Certifications

- **Master of Science, Computer Science** (2013 – 2015) — FAST-NUCES
- **Bachelor of Science, Computer Science** (2009 – 2013) — FAST-NUCES
- **AWS Certified Data Engineer - Associate** (DEA-C01)
- **Databricks Certified Data Engineer Professional**
- **SnowPro Core Certification** (Snowflake)
- **Microsoft Certified: Azure Data Engineer Associate** (DP-203)
- **Databricks Certified Generative AI Engineer Associate**
