# Chapter 5: Azure Data Engineering Topics

## Brief Information
Azure Data Engineering Topics cover data storage design, data processing, and security, monitoring, and optimization.

### Key Topics
- **Data Storage Design:** ADLS Gen2, Partitioning, Microsoft Purview.
- **Data Processing:** Batch vs. Streaming, ETL (Extract, Transform, Load).
- **Security, Monitoring & Optimization:** Data Masking, Encryption, Azure Monitor.

### Data Processing Concepts
- **Batch Processing:** Processing data in large chunks at specific intervals (e.g., nightly).
- **Streaming Processing:** Real-time data processing as it arrives (e.g., using Event Hubs).
- **ETL (Extract, Transform, Load):** Extracting data from sources, transforming it into a useful format, and loading it into a destination.

## Practical Example: Incremental Loading in ADF
Imagine you are loading data from a SQL database to a data lake.
1. **Initial Load:** You copy all 1 million rows from the SQL table to the data lake.
2. **Incremental Load:** Every night, you only copy the rows that have changed since the last load (e.g., rows with a `last_updated` date greater than the last successful load date).
3. **Trigger:** You schedule a trigger to run the pipeline every night at 2:00 AM.

## YouTube Tutorials
- [Azure Data Engineering Full Course - 12 Hours (Simplilearn)](https://www.youtube.com/watch?v=1vbXmCrkT3Y)
- [Azure Data Engineering Roadmap & Interview Prep (Codebasics)](https://www.youtube.com/watch?v=1vbXmCrkT3Y)
- [ETL vs. ELT Explained Simply](https://www.youtube.com/watch?v=NPEsD6n9A_I)
