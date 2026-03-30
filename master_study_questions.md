# Master Study Guide: 100 Hierarchical Questions on Data Architecture & Fundamentals

This guide is structured from foundational concepts to advanced architectural design. Use it to master the "why" and "how" of data engineering.

---

## Level 1: Big Data & Core Fundamentals (1-20)
*Focus: Storage, Processing, and the 4 Vs.*

1.  **What is the core definition of Big Data?** (Volume, Variety, Velocity, Veracity).
2.  **What is the difference between Structured, Semi-Structured, and Unstructured data?** Give examples.
3.  **Explain the "Schema-on-Read" vs. "Schema-on-Write" concept.** (Big Data vs. RDBMS).
4.  **What is the primary difference between Vertical Scaling and Horizontal Scaling?**
5.  **What are the two main components of Hadoop?** (HDFS for storage, MapReduce for processing).
6.  **How does HDFS achieve fault tolerance?** (Data replication across nodes).
7.  **What is the default block size in HDFS, and why is it so large?** (128MB to minimize disk seek time).
8.  **What is the role of the NameNode in HDFS?** (Manages metadata and block mapping).
9.  **What is the role of the DataNode?** (Stores actual data blocks).
10. **Explain the concept of "Heartbeats" in a distributed system.** (Worker nodes signalling availability).
11. **What is YARN, and what is its primary responsibility?** (Resource management and scheduling).
12. **What is the difference between a Master and a Worker node?** (Brain vs. Muscle).
13. **What is Hive, and how does it differ from a traditional SQL database?** (Data warehouse over HDFS).
14. **What is a "Metastore" in the context of Hive/Spark?** (Stores table definitions and metadata).
15. **What is SerDe?** (Serializer/Deserializer for reading/writing data).
16. **Explain the difference between Batch and Stream processing.**
17. **What is a "Data Lake"?** (Centralized repository for raw and structured data).
18. **What is a "Data Warehouse"?** (Optimized for structured, analytical querying).
19. **What is the "4th V" of Big Data (Veracity), and why is it important?** (Data quality and trust).
20. **What is Commodity Hardware, and why is it used in Big Data?** (Standard, inexpensive hardware for horizontal scaling).

---

## Level 2: Spark Internals & Optimization (21-40)
*Focus: Architecture, DAG, Catalyst, and Shuffling.*

21. **What is Apache Spark?** (Unified, in-memory analytics engine).
22. **Why is Spark faster than MapReduce?** (In-memory processing and Lazy Evaluation).
23. **What is the Spark Driver?** (The central coordinator that creates the DAG).
24. **What are Spark Executors?** (Worker processes that run tasks).
25. **Explain the Spark Cluster Manager.** (Allocates resources like YARN or Kubernetes).
26. **What is an RDD (Resilient Distributed Dataset)?** (Spark's basic, immutable abstraction).
27. **What is "Lazy Evaluation"?** (Transformations aren't executed until an Action is called).
28. **What is the difference between a Transformation and an Action?**
29. **What is a DAG (Directed Acyclic Graph)?** (The logical plan of execution).
30. **Explain the difference between Narrow and Wide Transformations.**
31. **What is a "Stage" in Spark execution?** (A set of tasks separated by shuffle boundaries).
32. **What is "Shuffling," and why is it expensive?** (Data movement across nodes over the network).
33. **What is the Catalyst Optimizer?** (Spark SQL's rule-based and cost-based optimizer).
34. **What is Project Tungsten?** (Optimizes memory/CPU via binary data and whole-stage code gen).
35. **What is a DataFrame in Spark?** (A structured, tabular representation of an RDD).
36. **What is a Dataset in Spark?** (Type-safe version of DataFrames, available in Scala/Java).
37. **What is Spark SQL?** (Module for structured data processing using SQL).
38. **What is "Caching" and "Persistence"?** (Storing intermediate results to avoid re-computation).
39. **When should you use `.cache()`?** (When the same DataFrame is used multiple times).
40. **What is "Data Skew" in Spark?** (Uneven data distribution causing stragglers).

---

## Level 3: Azure Data Ecosystem (41-60)
*Focus: ADLS Gen2, RBAC, Networking, and ADF.*

41. **What are the three main Cloud Service Models?** (IaaS, PaaS, SaaS).
42. **What is an Azure Region?** (A set of data centers within a latency-defined perimeter).
43. **What is an Azure Availability Zone?** (Physically separate data centers within a region).
44. **What is Azure Resource Manager (ARM)?** (The control plane for Azure resources).
45. **What is a Resource Group?** (A logical container for related resources).
46. **What is RBAC (Role-Based Access Control)?** (Managing access via roles and scopes).
47. **What is Azure Data Lake Storage (ADLS) Gen2?** (Built on Blob storage with Hierarchical Namespace).
48. **What is a Hierarchical Namespace (HNS), and why is it crucial for Big Data?** (Allows folder-level operations).
49. **Explain Hot, Cool, and Archive tiers in Azure Storage.**
50. **What is Azure Data Factory (ADF)?** (Cloud-based data integration and orchestration).
51. **What is a "Linked Service" in ADF?** (A connection string to an external resource).
52. **What is an "Integration Runtime" (IR) in ADF?** (The compute infrastructure for data movement).
53. **What is the difference between a Pipeline and an Activity in ADF?**
54. **What is a "Self-hosted Integration Runtime"?** (Used to access on-premises data).
55. **What is Azure Synapse Analytics?** (Unified analytics service for SQL, Spark, and Data Integration).
56. **What is the difference between Dedicated and Serverless SQL pools in Synapse?**
57. **What is Azure Event Hubs?** (A big data streaming platform and event ingestion service).
58. **What is Azure Monitor?** (Solution for collecting and analyzing telemetry).
59. **What is Azure Active Directory (Entra ID)?** (Identity and access management).
60. **What is a Virtual Network (VNet) in Azure?** (Provides isolation and security for cloud resources).

---

## Level 4: Databricks, Unity Catalog & Delta Lake (61-80)
*Focus: Lakehouse, Governance, and ACID.*

61. **What is the Databricks Lakehouse Architecture?** (Combines Data Lake and Data Warehouse).
62. **What is Delta Lake?** (Open-source storage layer that brings ACID to Data Lakes).
63. **Explain the ACID properties (Atomicity, Consistency, Isolation, Durability).**
64. **What is the "Transaction Log" in Delta Lake?** (Records every change made to the table).
65. **What is "Time Travel" in Delta Lake?** (Querying previous versions of a table).
66. **What is Unity Catalog?** (Unified governance for all data and AI assets in Databricks).
67. **What is a "Metastore" in Unity Catalog?** (Top-level container for metadata).
68. **Explain the Unity Catalog Three-Tier Namespace.** (`catalog.schema.table`).
69. **What is a "Managed Table" in Databricks?** (Data and metadata are both managed by Databricks).
70. **What is an "External Table"?** (Only metadata is managed; data stays in your storage).
71. **What is "Auto Loader" in Databricks?** (Efficiently ingests new files as they arrive).
72. **What are "Delta Live Tables" (DLT)?** (Declarative framework for building reliable data pipelines).
73. **What is the "Medallion Architecture"?** (Bronze, Silver, Gold layers).
74. **What is "Z-Ordering" in Delta Lake?** (Technique to co-locate related information for faster queries).
75. **What is "Data Skipping"?** (Optimization that skips reading irrelevant files using metadata).
76. **What is a "Databricks Workspace"?** (The environment for notebooks, clusters, and jobs).
77. **What is a "Databricks Cluster"?** (The compute resources used to run code).
78. **What is the difference between an Interactive Cluster and a Job Cluster?** (Development vs. Production).
79. **What is "Unity Catalog Sharing"?** (Securely sharing data with external organizations).
80. **What is a "Catalog" in Unity Catalog?** (A grouping of schemas, used to manage access).

---

## Level 5: Advanced Architecture & Design Patterns (81-100)
*Focus: Security, Performance Tuning, and Modern Data Patterns.*

81. **What is the Lambda Architecture?** (Batch + Speed layers).
82. **What is the Kappa Architecture?** (Stream processing only).
83. **What is "Idempotency," and why is it critical in data pipelines?** (Ensures same result regardless of retries).
84. **What is "Data Lineage"?** (Tracking data from source to destination).
85. **How do you handle "Slowly Changing Dimensions" (SCD Type 1 vs. Type 2)?**
86. **What is "Predicate Pushdown"?** (Filtering data at the source to reduce data read).
87. **What is "Projection Pruning"?** (Reading only the required columns).
88. **Explain the concept of "Partition Pruning."** (Skipping entire folders based on query filters).
89. **What is "Data Masking," and how is it implemented?** (Hiding sensitive data from unauthorized users).
90. **What is "Data Encryption at Rest" vs. "In Transit"?**
91. **What is "Zero Trust Security"?** (Always verify, never trust).
92. **How do you handle "Small File Problem" in Spark?** (Use `coalesce` or `repartition`).
93. **What is the difference between `repartition()` and `coalesce()`?** (Full shuffle vs. reducing partitions without shuffle).
94. **What is "Whole-Stage Code Generation"?** (Fusing multiple operators into one function).
95. **What is a "Broadcast Join"?** (Sending a small table to all nodes to avoid a full shuffle).
96. **What is "Spill to Disk"?** (When Spark memory is full and writes to disk, causing slowdowns).
97. **What is a "Tumbling Window" vs. "Sliding Window" in streaming?**
98. **What is "Watermarking" in Structured Streaming?** (Handling late-arriving data).
99. **What is "Data Mesh"?** (Decentralized data architecture organized by business domains).
100. **What is "Data Fabric"?** (An architectural layer that connects disparate data sources).

---
