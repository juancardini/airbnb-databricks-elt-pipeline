# 🏡 Airbnb Databricks ELT Pipeline

End-to-end **ELT pipeline** built with **Databricks, PySpark, and Delta Lake**, following the **Medallion Architecture (Bronze → Silver → Gold)**.

---

## 📖 Overview

This project implements a complete ELT pipeline using Airbnb listings data. The pipeline ingests raw CSV files, performs data cleansing and validation, and generates business-ready datasets optimized for analytics and reporting.

---

## 🏗️ Architecture

The solution follows the **Medallion Architecture**:

### 🥉 Bronze Layer (Raw)

- Load raw Airbnb CSV files
- Normalize column names
- Store data as Delta tables
- Preserve raw data with minimal transformations

### 🥈 Silver Layer (Clean)

- Data type conversions (`integer`, `double`, `date`)
- Trim and clean string columns
- Handle null values
- Remove or identify duplicate records
- Apply data quality validations
- Standardize datasets

### 🥇 Gold Layer (Business)

- Build business-ready tables
- Generate aggregated KPIs
- Compute metrics by:
  - Neighbourhood
  - Room type
- Prepare datasets for BI and analytics

---

## ⚙️ Tech Stack

- **Databricks**
- **PySpark**
- **Delta Lake**
- **Spark SQL**
- **Python**

---

## 🔄 Pipeline Flow

```text
CSV Files
    │
    ▼
Bronze (Raw)
    │
    ▼
Silver (Clean & Validated)
    │
    ▼
Gold (Business Aggregations)
```

### 1. Data Ingestion

- Read Airbnb CSV files from Databricks Volumes
- Create Bronze Delta tables

### 2. Data Transformation

- Clean column names
- Standardize data types
- Trim string values
- Validate data quality
- Detect duplicates

### 3. Business Aggregations

Generate KPIs including:

- Average listing price
- Listings by neighbourhood
- Listings by room type
- Other business metrics

---

## ✅ Data Quality Checks

The pipeline includes several validation steps:

- ✔️ Row count validation between Bronze and Silver
- ✔️ Null value analysis
- ✔️ Duplicate detection using the listing `id`
- ✔️ Invalid record filtering
- ✔️ Schema validation
- ✔️ Data type verification

---

## 📊 Example KPIs

- Average price by neighbourhood
- Average price by room type
- Total listings per neighbourhood
- Total listings per room type

---

## 📂 Project Structure

```text
airbnb-databricks-elt-pipeline/
│
├── notebooks/
│   ├── 01_bronze_ingestion.py
│   ├── 02_silver_transformation.py
│   └── 03_gold_aggregation.py
│
├── images/
│   └── architecture.png
│
└── README.md
```

---

## 🚀 Key Features

- Medallion Architecture
- Delta Lake tables
- Data Quality validations
- PySpark transformations
- Incremental-ready pipeline
- Business KPI generation
