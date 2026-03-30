# Chapter 9: Azure DevOps & Key Vault

## Brief Information
Azure DevOps & Key Vault are essential for managing code, secrets, and infrastructure in a secure and automated way.

### Key Components
- **Azure Key Vault:** A cloud service for securely storing and accessing secrets (e.g., API keys, passwords, certificates).
- **Continuous Integration (CI):** The practice of automating the integration of code changes into a shared repository.
- **Continuous Delivery & Deployment (CD):** The practice of automatically deploying code changes to various environments (e.g., Development, Staging, Production).

### Infrastructure as Code (IaC)
- **IaC:** Managing and provisioning infrastructure through code instead of manual processes.
- **Tools:** ARM templates, Terraform, Ansible.

## Practical Example: Azure Key Vault Integration in ADF
Imagine you are storing a SQL connection string in Azure Key Vault.
1. **Create Secret:** In Key Vault, create a secret called `SqlConnectionString`.
2. **Assign Permissions:** Give ADF "Get" access to the secret in Key Vault.
3. **Reference Secret:** In ADF, use the secret name in the linked service configuration.
4. **Deploy Pipeline:** The connection string is now securely accessed by ADF at runtime.

## YouTube Tutorials
- [Azure DevOps Full Course - 12 Hours (Simplilearn)](https://www.youtube.com/watch?v=1vbXmCrkT3Y)
- [Azure Key Vault Explained Simply (Programming with Mosh)](https://www.youtube.com/watch?v=_C8kWso4ne4)
- [CI/CD Pipelines with Azure DevOps Tutorial - Microsoft Learn](https://www.youtube.com/watch?v=1vbXmCrkT3Y)
