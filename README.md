Data-Engineering-Fundamentals
Assignments On Data Engineering

Data Engineering Assignment 01

🟦 01 — ETL & ELT Tools

In Data Engineering, the difference between ETL and ELT lies in where the transformation happens.

ETL (Extract → Transform → Load):
Data is transformed before loading into the data warehouse.

ELT (Extract → Load → Transform):
Raw data is loaded into the warehouse first, and transformations happen inside the warehouse using its compute power.

✅ 3 Common ETL Tools
1. Talend

Popular open-source and enterprise ETL platform

Ideal for batch workflows and complex integrations

2. Apache NiFi

Great for real-time data ingestion

Drag-and-drop UI for routing and transforming data flows

3. Informatica PowerCenter

Enterprise-grade ETL tool used in large organizations

Highly stable and reliable for on-premise and hybrid ETL workflows

Note (as a Python Developer):
Custom ETL using Python + Pandas + Airflow DAGs is also very common in modern data engineering.

🟩 3 Common ELT Tools
1. dbt (Data Build Tool)

The industry standard for ELT

Runs SQL transformations directly inside Snowflake, BigQuery, or Redshift

Supports modular SQL, version control, and testing

2. Fivetran

Handles Extract + Load automatically from multiple SaaS sources

Assumes transformations will happen later in the warehouse (with dbt or SQL)

3. Matillion

Cloud-native ELT platform

Designed specifically for Snowflake, Redshift, and BigQuery

Pushes SQL transformations directly down to the warehouse’s compute layer

🟧 02 — Cloud Zones in Data Engineering

Modern data lakes follow a multi-zone architecture to manage data quality, processing, and consumption.

Below are the three main zones:

1. Landing Zone (Raw Zone / Bronze Layer)

Stores raw, unprocessed source data

No schema enforcement

Examples: API responses, CSV dumps, logs

Used as a single source of truth for incoming data

2. Processing Zone (Clean Zone / Silver Layer)

Data is cleaned and validated

Handles duplicates, missing values, and type conversions

Standardizes data for downstream consumption

Used mostly by Data Engineers

3. Curated Zone (Analytics / Gold Layer)

Final business-ready datasets

Used for dashboards, reporting, and ML

Aggregations, fact tables, and dimension tables live here

Highly trusted and optimized
