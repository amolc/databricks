# Chapter 11: Foundational Deep Dive & Terminology

## Brief Information
This section addresses the core conceptual gaps identified in the feedback. Mastering these terms and concepts is critical for the re-evaluation.

### Key Architecture & Design Patterns
- **Lambda Architecture:** A data-processing architecture designed to handle massive quantities of data by taking advantage of both batch and stream-processing methods.
- **Kappa Architecture:** A simplification of Lambda architecture. A software architecture pattern that treats all data as a stream and uses a single stream-processing engine.
- **Data Lakehouse:** A new, open data management architecture that combines the flexibility, cost-efficiency, and scale of data lakes with the data management and ACID transactions of data warehouses.
- **Medallion Architecture:** A data design pattern used to logically organize data in a lakehouse.
  - **Bronze (Raw):** Landing zone for raw data. No transformations.
  - **Silver (Cleansed/Enriched):** Data is filtered, cleaned, and joined. The "Single Source of Truth".
  - **Gold (Curated):** Business-level aggregates, ready for BI and reporting.

### Data Reliability & Transactions
- **ACID Properties:** 
  - **Atomicity:** All or nothing.
  - **Consistency:** Data remains in a valid state.
  - **Isolation:** Transactions don't interfere with each other.
  - **Durability:** Data is permanently saved once committed.
- **Idempotency:** An operation that can be performed multiple times without changing the result beyond the initial application. (Crucial for data pipelines and retries).
- **Data Lineage:** The "pedigree" of data. Tracking where data comes from, how it's transformed, and where it goes.

### Processing Concepts
- **Data Skew:** When data is not evenly distributed across partitions, causing some worker nodes to work much harder than others.
- **Spill to Disk:** When Spark's memory is insufficient, it writes intermediate data to disk, significantly slowing down the process.
- **Predicate Pushdown:** An optimization where filtering is pushed as close to the data source as possible to reduce the amount of data read.
- **Projection Pruning:** An optimization where only the required columns are read from the data source.

### Essential Terminology Glossary
- **Compute:** The CPU and RAM resources used to process data.
- **Storage:** The physical location where data is kept (e.g., Disk, Cloud Storage).
- **Orchestration:** Coordinating the execution of multiple tasks/pipelines (e.g., ADF, Airflow).
- **Schema-on-Write:** Traditional RDBMS. You must define the schema before loading data.
- **Schema-on-Read:** Big Data systems. Data is stored raw, and the schema is applied when it's read.
- **Upsert:** A combination of `UPDATE` and `INSERT`. (e.g., `MERGE` in Delta Lake).
- **CDC (Change Data Capture):** A process that identifies and captures changes made to data in a source database and delivers those changes in real-time to a target system.

## Practical Example: Medallion Architecture Implementation
Imagine you are building a data solution for a retail company.
1. **Bronze Layer:** Use ADF to copy raw sales data from a SQL database to a data lake.
2. **Silver Layer:** Use Databricks to clean and transform the raw sales data using PySpark.
3. **Gold Layer:** Use Databricks to aggregate the cleaned sales data per day and per store.
4. **Power BI Dashboard:** Use Power BI to visualize the aggregated sales data from the Gold layer.

## YouTube Tutorials
- [Data Lakehouse Architecture Explained Simply](https://www.youtube.com/watch?v=NPEsD6n9A_I)
- [Medallion Architecture & Data Engineering Roadmap (Codebasics)](https://www.youtube.com/watch?v=1vbXmCrkT3Y)
- [ACID Properties & Data Reliability Explained (Programming with Mosh)](https://www.youtube.com/watch?v=_C8kWso4ne4)
