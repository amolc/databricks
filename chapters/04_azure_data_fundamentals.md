# Chapter 4: Microsoft Azure Data Fundamentals

## Brief Information
Microsoft Azure Data Fundamentals covers core data concepts, including relational and non-relational data, and analytics workloads.

### Key Data Concepts
- **The Data Lifecycle:** Ingest (ADF), Store (ADLS Gen2), Process/Train (Databricks), Model/Serve (Synapse, Power BI).
- **Relational vs. Non-Relational:** SQL (structured) vs. NoSQL (unstructured).
- **Analytical vs. Transactional Systems:** 
  - **OLTP (Transactional):** High volume of small transactions (e.g., banking).
  - **OLAP (Analytical):** Low volume of complex queries (e.g., BI reports).

### Data Storage Terminology
- **Blob Storage:** Object storage for unstructured data.
- **ADLS Gen2 (Azure Data Lake Storage):** Built on Blob storage with a **Hierarchical Namespace (HNS)**. HNS allows for folder-level operations and POSIX-compliant ACLs.
- **Hot vs. Cool vs. Archive Tiers:** 
  - **Hot:** Frequent access.
  - **Cool:** Infrequent access (30+ days).
  - **Archive:** Rarely accessed (180+ days).

## Practical Example: Data Tiering in ADLS Gen2
Imagine you are storing daily sales data.
1. **Hot Tier:** You keep the current month's data in the Hot tier for daily reports.
2. **Cool Tier:** After 30 days, you move the data to the Cool tier to save storage costs.
3. **Archive Tier:** After one year, you move the data to the Archive tier for long-term compliance storage.

## YouTube Tutorials
- [Azure Data Fundamentals Certification Course (DP-900) - Full Course (FreeCodeCamp)](https://www.youtube.com/watch?v=N_7U2_N7D_U)
- [Microsoft Azure Data Fundamentals (DP-900) - 10 Hours (Simplilearn)](https://www.youtube.com/watch?v=1vbXmCrkT3Y)
- [Azure Data Lake Gen2 Explained Simply](https://www.youtube.com/watch?v=NPEsD6n9A_I)
