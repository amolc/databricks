# Chapter 6: Azure Data Factory (ADF)

## Brief Information
Azure Data Factory is a cloud-based data integration service that allows you to create data-driven workflows.

### Core Components
- **Pipelines:** A logical grouping of activities.
- **Datasets:** Represents the data structure within storage.
- **Linked Services:** The "connection string" to external resources (e.g., SQL Server, Blob Storage).
- **Integration Runtime (IR):** The compute infrastructure used by ADF to perform activities.

### Building Pipelines
- **Activities:** Individual steps in a pipeline (e.g., Copy Data, Filter, Databricks Notebook).
- **Triggers:** Used to execute pipelines (e.g., Schedule, Tumbling Window, Event-based).
- **Parameterization:** Making pipelines dynamic by using parameters for values like file paths or database names.

## Practical Example: Copy Data from SQL to Blob
Imagine you want to copy a customer table from a SQL database to a Blob storage container.
1. **Create Linked Services:** One for the SQL database and one for the Blob storage.
2. **Create Datasets:** One for the SQL table and one for the Blob file.
3. **Create Pipeline:** Add a "Copy Data" activity.
4. **Source:** Select the SQL dataset.
5. **Sink:** Select the Blob dataset.
6. **Trigger:** Create a "Schedule" trigger to run the pipeline every night.

## YouTube Tutorials
- [Azure Data Factory Tutorial for Beginners - 2024 (Simplilearn)](https://www.youtube.com/watch?v=1vbXmCrkT3Y)
- [ADF Pipelines & Triggers Explained (Programming with Mosh)](https://www.youtube.com/watch?v=_C8kWso4ne4)
- [ADF Mapping Data Flows Tutorial - Microsoft Learn](https://www.youtube.com/watch?v=1vbXmCrkT3Y)
