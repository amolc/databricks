# Chapter 2: Spark Essentials

## Brief Information
Apache Spark is a unified analytics engine for large-scale data processing. It is up to 100x faster than MapReduce because it processes data **in-memory** and uses **Lazy Evaluation**.

### Key Architecture Components
- **Driver:** The process where `main()` runs. It converts user code into a **DAG (Directed Acyclic Graph)**.
- **Executors:** Worker nodes that execute tasks and store data.
- **Catalyst Optimizer:** Optimizes SQL queries by analyzing, logically optimizing, and physically planning.
- **Project Tungsten:** Optimizes memory and CPU usage by avoiding Java GC overhead.

## Practical Example: PySpark Data Transformation
Imagine you have a CSV file of customer transactions and want to find the total spending per customer.
```python
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("CustomerSpend").getOrCreate()

# 1. Read the data
df = spark.read.csv("transactions.csv", header=True, inferSchema=True)

# 2. Transformation (Lazy Evaluation)
# Select specific columns and filter for high-value transactions
high_value_df = df.select("customer_id", "amount").filter(df.amount > 100)

# 3. Aggregation (Wide Transformation - Shuffling occurs)
total_spend = high_value_df.groupBy("customer_id").sum("amount")

# 4. Action (Triggers computation)
total_spend.show()
```

## YouTube Tutorials
- [Apache Spark Full Course - 10 Hours (Simplilearn)](https://www.youtube.com/watch?v=d_U0V6d_U_o)
- [PySpark Tutorial for Beginners - 2024 (Programming with Mosh)](https://www.youtube.com/watch?v=_C8kWso4ne4)
- [Spark Architecture & DAG Explained](https://www.youtube.com/watch?v=Xv1p_6I8Kk0)
