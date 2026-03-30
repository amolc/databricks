# Chapter 7: Azure Databricks

## Brief Information
Azure Databricks is a cloud-based Big Data analytics platform built on Apache Spark.

### Core Concepts
- **Notebooks:** Interactive environments for writing code in Python, SQL, Scala, and R.
- **Clusters:** The compute resources used to run code.
- **Job Scheduling:** Automating the execution of notebooks or JAR files at specific times or based on events.

### Data Engineering on Databricks
- **ETL with PySpark:** Using the Spark DataFrame API to extract, transform, and load data.
- **Delta Lake Operations:**
  - **MERGE:** Combines `INSERT` and `UPDATE` into a single operation (Upsert).
  - **Time Travel:** Allows you to query historical versions of your data.
  - **Auto Loader:** Efficiently processes new files arriving in cloud storage.

## Practical Example: Delta Lake Upsert (MERGE)
Imagine you have a new set of customer data that you want to merge into an existing Delta table.
```sql
-- Existing Delta table: customers
-- New data: new_customers

MERGE INTO customers
USING new_customers
ON customers.id = new_customers.id
WHEN MATCHED THEN
  UPDATE SET *
WHEN NOT MATCHED THEN
  INSERT *
```

## YouTube Tutorials
- [Azure Databricks & Spark Masterclass - 2024 (Simplilearn)](https://www.youtube.com/watch?v=1vbXmCrkT3Y)
- [Delta Lake & Lakehouse Architecture Explained (Programming with Mosh)](https://www.youtube.com/watch?v=_C8kWso4ne4)
- [Databricks SQL & Dashboarding Tutorial - Microsoft Learn](https://www.youtube.com/watch?v=1vbXmCrkT3Y)
