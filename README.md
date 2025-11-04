# Databricks Hospital BI Platform

> A unified healthcare analytics platform demonstrating end-to-end data engineering with Databricks Medallion Architecture, from raw data ingestion to interactive Power BI dashboards.
---

## 🎯 Project Overview

This project bridges theory with real-world implementation, applying advanced data engineering patterns to solve healthcare data integration challenges. It demonstrates how to build a production-ready data pipeline that transforms fragmented healthcare data (EHR, Insurance, Billing) into actionable insights for clinical, operational, and financial analytics.

![Workflow](https://github.com/anhvi02/Databricks_Hospital_BI_Platform/blob/main/workflow.png?raw=true)

**Key Highlights:**
- End-to-end Medallion Architecture (Bronze → Silver → Gold)
- Data storage with S3
- Auto Loader for incremental data ingestion
- Pipeline Orchestration with Databricks Jobs
- Power BI integration with DirectQuery

---

## 🏗️ Architecture

### Solution Overview
![Solution Architecture](https://github.com/anhvi02/Databricks_Hospital_BI_Platform/blob/main/architecture.png?raw=true)

### Medallion Architecture Layers

#### 🥉 Bronze Layer
- **Purpose:** Raw data ingestion with full audit trail
- **Technology:** Auto Loader + Delta Lake
- **Features:**
  - Incremental file processing from AWS S3
  - Automatic schema inference and evolution
  - No transformations - preserves data lineage
  - Checkpoint management for reliable recovery

#### 🥈 Silver Layer
- **Purpose:** Data cleansing and business rule application
- **Technology:** PySpark + Delta Lake
- **Features:**
  - Comprehensive data cleaning and validation
  - Derived column calculations (length of stay, treatment metrics)
  - **Quarantine Strategy:** Isolates invalid data for review
  - Business logic implementation
  - Data quality constraints

#### 🥇 Gold Layer
- **Purpose:** Analytics-ready datasets for BI consumption
- **Technology:** SQL + Materialized Views + Delta Lake
- **Features:**
  - Star schema implementation
  - Pre-calculated KPIs and aggregations
  - Liquid clustering for query optimization
  - Optimized for Power BI DirectQuery

---

## ⚡ Data Pipeline

### Delta Live Tables Implementation

The pipeline follows a DAG (Directed Acyclic Graph) pattern with event-based orchestration:
![Databricks Pipeline](https://github.com/anhvi02/Databricks_Hospital_BI_Platform/blob/main/databricks_pipeline.png?raw=true)

### Pipeline Features

- **Orchestration:** Databricks Lakeflow with event-based triggers
- **Monitoring:** Email notifications for pipeline status
- **Processing:** File-based batch processing (streaming-ready architecture)
- **Execution:** Automatic trigger on new data arrival in S3
- **Parallelization:** Independent notebook execution for parallel processing

---

## 📊 Dashboard & Analytics
![PowerBI Dashboard](https://github.com/anhvi02/Databricks_Hospital_BI_Platform/blob/main/powerbi_dashboard.png?raw=true)

### Power BI Integration

- **Connection:** DirectQuery to Databricks SQL endpoint
- **Data Source:** Gold layer tables and materialized views
- **Refresh:** Scheduled updates + user-triggered via PowerAutomate
- **Performance:** Optimized queries leveraging Delta Lake's indexing

### Key Metrics & Visualizations

**Financial Performance:**
- Total Revenue with target comparison
- Revenue by Department (General Surgery, Orthopedics, Neurology, Cardiology, Pediatrics)
- Patient Payment vs Insurance Coverage trends
- Revenue by Referral Sources (Emergency, Physician, Self-Referral)
- Service Revenue breakdown (Medication, Room, Treatment)
- Monthly revenue with MoM % change

**Operational Metrics:**
- Total Patients and Visits with trend indicators
- Visit type distribution (Emergency vs Follow-up)
- Time-period analysis and KPI monitoring

---

## 🛠️ Technology Stack

### Data Platform
- **Databricks:** Unified analytics platform
- **Delta Lake:** ACID-compliant storage layer
- **Apache Spark:** Distributed processing
- **PySpark:** Data transformation

### Data Storage & Orchestration
- **AWS S3:** Cloud object storage
- **Auto Loader:** Incremental ingestion
- **Unity Catalog:** Data governance
- **Databricks Jobs:** Pipeline Orchestration

### Business Intelligence
- **Power BI:** Data visualization
- **DirectQuery:** Real-time connectivity
- **PowerAutomate:** Workflow automation


---

## 💡 Key Technical Learnings

### Databricks Platform
- **Unified workspace** eliminates traditional data engineering friction points
- **Auto Loader** simplifies incremental data ingestion with schema evolution
- **Delta Lake** ensures data reliability with ACID transactions and time travel
- **Unity Catalog** provides robust governance and lineage tracking

### Data Engineering Patterns
- **Medallion Architecture** enables clear separation of concerns across layers
- **Quarantine strategy** improves data quality through systematic isolation of invalid records
- **Materialized views** optimize query performance for BI workloads
- **Event-based orchestration** enables near-real-time pipeline execution

### BI Integration
- **DirectQuery** provides real-time analytics without data duplication
- **SQL endpoints** deliver fast query performance for interactive dashboards
- **Gold layer optimization** (clustering, Z-ordering) improves response times

---

## 👤 Author

**Anh Vi**
- GitHub: [@anhvi02](https://github.com/anhvi02)
- LinkedIn: [Connect with me](https://www.linkedin.com/in/anh-vi-pham/)

---

<div align="center">

**⭐ If you find this project helpful, please give it a star! ⭐**

</div>