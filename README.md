# airbnb-databricks-elt-pipeline
Airbnb ETL Pipeline with Databricks (Bronze-Silver-Gold)
Overview
This project implements an end-to-end ELT pipeline using Airbnb listings data, following a modern Medallion Architecture (Bronze, Silver, Gold) in Databricks with PySpark and Delta Lake.
The pipeline ingests raw data, performs data cleaning and validation, and produces business-ready aggregated tables for analytics.
Architecture
The pipeline is structured into three layers:
Bronze (Raw Layer)
•	Ingest raw CSV data using PySpark
•	Normalize column names
•	Store data in Delta Lake
Silver (Clean Layer)
•	Type casting (int, float, double, date)
•	String cleaning (trim)
•	Data validation (null checks, filtering invalid records)
•	Duplicate detection
Gold (Business Layer)
•	Aggregated KPIs for analytics
•	Grouped metrics by neighbourhood and room type
•	Business-ready datasets for BI tools
Tech Stack
•	PySpark
•	Databricks
•	Delta Lake
•	SQL
Data Pipeline Flow
1.	Ingestion
o	Load Airbnb CSV data from Databricks Volume
2.	Transformation
o	Clean and standardize columns
o	Convert data types
o	Validate data quality
3.	Aggregation
o	Compute KPIs such as:
	Average price
	Listings per neighbourhood
	Listings per room type
Data Quality Checks
•	Row count validation (Bronze vs Silver)
•	Null value analysis per column
•	Duplicate detection on primary key (id)
•	Filtering invalid records (e.g., null prices)

