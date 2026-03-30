# Frequently Asked Questions (FAQ)

This FAQ addresses common questions and foundational concepts crucial for the data engineering evaluation.

---

### **1. What is Unity Catalog?**
**Unity Catalog** is a unified governance solution for all data and AI assets in the Databricks Lakehouse. It provides a single place to manage access permissions, data lineage, and data sharing across different Databricks workspaces.

**Key Features:**
- **Centralized Access Control:** Define permissions (GRANT/REVOKE) at the account level instead of the workspace level.
- **Data Lineage:** Automatically capture end-to-end lineage (which user ran what query on which table).
- **Unity Catalog Metastore:** A three-tier namespace (`catalog.schema.table`) that replaces the legacy two-tier Hive Metastore.
- **Data Sharing:** Securely share data with other organizations using Delta Sharing.

---

### **2. What comes first: Unity Catalog or Data Lake?**
The **Data Lake (ADLS Gen2/S3)** always comes first. 

**The Hierarchy:**
1. **Data Lake (Physical Storage):** You first need a place to store your actual data files (Parquet, Delta, CSV).
2. **External Location:** You define a connection between Databricks and the Data Lake.
3. **Unity Catalog (Governance Layer):** You then wrap the Unity Catalog *over* the Data Lake to manage who can see and use that data.

*Think of the Data Lake as the warehouse (physical building) and Unity Catalog as the security system and inventory manager (software/rules).*

---

### **3. What is the difference between a Managed Table and an External Table?**
- **Managed Table:** Databricks manages both the metadata and the physical data. If you `DROP` the table, the data in storage is also deleted.
- **External Table:** Databricks only manages the metadata. You provide a path to the existing data in your Data Lake. If you `DROP` the table, the data remains in your storage.

---

### **4. Why is Delta Lake preferred over Parquet for Lakehouse architectures?**
While Delta Lake uses Parquet as its underlying storage format, it adds a **Transaction Log**. This enables:
- **ACID Transactions:** Prevents data corruption during concurrent writes.
- **Time Travel:** Ability to query older versions of data.
- **Schema Enforcement:** Prevents "junk" data from breaking your pipelines.
- **Upserts (MERGE):** Efficiently handling updates and inserts.

---

### **5. What is the role of the Driver vs. Executor in Spark?**
- **Driver:** The "Brain." It hosts the SparkSession, analyzes the code, creates the DAG, and schedules tasks.
- **Executor:** The "Muscle." It resides on worker nodes, executes the tasks assigned by the driver, and stores data in memory or disk.

---

### **6. What is the difference between Azure Data Factory (ADF) and Databricks?**
- **ADF:** Primarily an **Orchestrator**. Best for moving data (Copy Activity) and scheduling complex workflows. It is "low-code."
- **Databricks:** Primarily a **Processing Engine**. Best for complex transformations, data science, and heavy-duty data engineering using Spark. It is "code-first" (Python/SQL).

---

### **7. What is "Data Skew" and why is it a problem?**
Data Skew occurs when data is not distributed evenly across partitions. For example, if 90% of your sales data belongs to one "Store ID," one Spark executor will work much longer than others. This leads to **Stragglers** (tasks that take forever) and inefficient cluster usage.

---

### **8. What is the Medallion Architecture?**
It is a data design pattern to organize data logically:
- **Bronze:** Raw data (as-is from source).
- **Silver:** Cleaned, filtered, and augmented data (Single Source of Truth).
- **Gold:** Aggregated business-level data (Ready for Power BI/Reporting).

---
