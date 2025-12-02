# Data-Engineering-Fundamentals
Assignments On Data Engineering

# Data Engineering Assignment 01

## 1. ETL vs ELT Tools

### ETL (Extract, Transform, Load)
*Data is transformed on a secondary server before loading.*
1. **Talend** - Open-source integration.
2. **Apache NiFi** - Automated data flow/ingestion.
3. **Informatica PowerCenter** - Enterprise-grade on-premise/hybrid tool.

### ELT (Extract, Load, Transform)
*Data is loaded raw; transformations happen inside the warehouse.*
1. **dbt (data build tool)** - Runs SQL transformation inside warehouses.
2. **Fivetran** - Automated connectors for SaaS to Warehouse.
3. **Matillion** - Cloud-native solution for Snowflake/Redshift.

---

## 2. Research Cloud Zones

**Definition:** "Zones" refers to **Availability Zones (AZs)**, which are physically separate data centers within a specific Region (e.g., `us-east-1a`).

**Importance in Data Engineering:**
* **High Availability:** Distributing pipelines across AZs ensures continuity if one data center fails.
* **Latency:** Compute resources (like EC2) should be in the same AZ as storage to maximize speed.
* **Cost:** Data transfer between AZs often incurs costs, unlike local transfer.

---

## 3. Source -> BI Flow Diagram

```mermaid
flowchart LR
    subgraph Sources
    A[APIs / DBs / Files]
    end

    subgraph Ingestion
    B[Staging / Data Lake]
    end

    subgraph Warehouse
    C[(Data Warehouse)]
    end

    subgraph BI
    D[Dashboards / Reporting]
    end

    A -- Extract --> B
    B -- Load --> C
    C -- Transform (dbt) --> C
    C -- Serve --> D
