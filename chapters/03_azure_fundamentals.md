# Chapter 3: Microsoft Azure Fundamentals

## Brief Information
Microsoft Azure is a cloud computing platform that provides a wide range of services. It is divided into **Regions** and **Availability Zones**.

### Key Service Models
- **IaaS (Infrastructure as a Service):** You manage the OS, middleware, and apps (e.g., Azure VMs).
- **PaaS (Platform as a Service):** You manage only the apps and data (e.g., Azure SQL, Databricks).
- **SaaS (Software as a Service):** You just use the software (e.g., Microsoft 365).

### Resource Management
- **Control Plane (ARM):** The management layer for creating, updating, and deleting resources.
- **Data Plane:** The layer where the actual service functionality happens.
- **RBAC (Role-Based Access Control):** Granular access management (Scope: Subscription -> Resource Group -> Resource).

## Practical Example: Azure Resource Group Organization
Imagine you are building a new data project.
1. **Create a Subscription:** This is where you are billed.
2. **Create a Resource Group:** You create a group called `SalesDataProject-RG`.
3. **Deploy Resources:** Inside this group, you deploy an Azure Data Lake Gen2, a Databricks workspace, and an Azure Data Factory instance.
4. **Apply RBAC:** You give your data engineers "Contributor" access to the resource group, but give your data analysts only "Reader" access to the data lake.

## YouTube Tutorials
- [Azure Fundamentals Certification Course (AZ-900) - Full Course (FreeCodeCamp)](https://www.youtube.com/watch?v=NPEsD6n9A_I)
- [Microsoft Azure Full Course - 12 Hours (Edureka)](https://www.youtube.com/watch?v=1vbXmCrkT3Y)
- [Azure Networking Fundamentals Explained Simply](https://www.youtube.com/watch?v=4x9qXq8hP_k)
