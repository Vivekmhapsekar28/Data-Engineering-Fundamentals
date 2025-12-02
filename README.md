# Data Engineering Assignment 01

---

# 01 — ETL & ELT Tools

In Data Engineering, the difference between ETL and ELT lies in **where the transformation happens**.

- **ETL (Extract → Transform → Load):**  
  Data is transformed *before* loading into the data warehouse.

- **ELT (Extract → Load → Transform):**  
  Raw data is loaded into the warehouse first, and transformations happen *inside* the warehouse using its compute power.

---

## 3 Common ETL Tools

### **1. Talend**
- Popular open-source and enterprise ETL platform  
- Ideal for batch workflows and complex integrations  

### **2. Apache NiFi**
- Great for real-time data ingestion  
- Drag-and-drop UI for routing and transforming data flows  

### **3. Informatica PowerCenter**
- Enterprise-grade ETL tool used in large organizations  
- Highly stable and reliable for on-premise and hybrid ETL workflows  

---

## 3 Common ELT Tools

### **1. dbt (Data Build Tool)**
- The industry standard for ELT  
- Runs SQL transformations directly inside Snowflake, BigQuery, or Redshift  
- Supports modular SQL, version control, and testing  

### **2. Fivetran**
- Handles **Extract + Load** automatically from SaaS sources  
- Pairs well with dbt for SQL transformations  

### **3. Matillion**
- Cloud-native ELT tool  
- Designed for Snowflake, Redshift, and BigQuery  
- Pushes SQL transformations down to the warehouse compute layer  

---

# 02 — Cloud Zones in Data Engineering

Modern data lakes follow a **multi-zone architecture** to manage data quality, processing, and consumption.

---

## **1. Landing Zone (Raw Zone / Bronze Layer)**
- Stores raw, unprocessed source data  
- No schema enforcement  
- Examples: API responses, CSV dumps, logs  
- Serves as a single source of truth  

---

## **2. Processing Zone (Clean Zone / Silver Layer)**
- Data is cleaned and validated  
- Handles duplicates, missing values, and type conversions  
- Standardized for downstream pipelines  

---

## **3. Curated Zone (Analytics / Gold Layer)**
- Final business-ready datasets  
- Used for BI reporting and ML  
- Contains aggregated and optimized tables  

---

# 🟨 03 — Source → BI Flow Diagram

Below is the complete data flow from source systems to BI dashboards.

```
            +-------------------+
            |    Source Data    |
            | (APIs, DBs, Logs) |
            +---------+---------+
                      |
                      v
          +-----------------------+
          |   Landing Zone (Raw)  |
          +-----------------------+
                      |
                      v
          +-----------------------+
          | Processing Zone       |
          | (Cleaning, Validation)|
          +-----------------------+
                      |
                      v
          +-----------------------+
          | Curated Zone (Gold)   |
          | Analytics-ready data  |
          +-----------------------+
                      |
                      v
           +----------------------+
           |  BI Tools / Reports  |
           | (Power BI, Tableau)  |
           +----------------------+
```
