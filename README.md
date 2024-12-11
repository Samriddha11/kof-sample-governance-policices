# Azure Harness Asset Governance Policies

This repository contains a collection of **Harness Asset Governance** policies to manage **Azure resources**, including Storage Accounts, SQL Servers, Cosmos DB, and more. These policies focus on enhancing security, optimizing costs, ensuring compliance, and maintaining operational efficiency.

---

## Table of Policies

| **Service**   | **Policy Name**                        | **Objective**                    | **Description**                                                                 |
|---------------|---------------------------------------|---------------------------------|-----------------------------------------------------------------------------|
| **Storage**    |sec-enforce-storage-encryption          | Data at Rest Encryption         | Ensures encryption at rest for all data in Azure Storage Accounts.            |
|               | sec-restrict-public-access              | Secure Storage Account Access  | Disables public access to storage accounts, allowing only private access.   |
|               | sec-enforce-storage-firewall-rules  | IP Access Control                | Limits access only to specified IP addresses to secure storage accounts.    |
|               | cost-enable-soft-delete        | Prevent Data Loss               | Protects against accidental deletions by retaining deleted blobs.            |
|               | sec-enforce-secure-transfer        | Secure Data Transmission        | Forces communication with storage accounts to use HTTPS.                    |
|               | cost-delete-inactive-blobs             | Optimize Storage Costs          | Automatically deletes blobs that haven't been accessed for more than 90 days. |
|               | cost-lifecycle-management-tiers      | Cost Optimization               | Moves data across storage tiers (Hot, Cool, Archive) according to lifecycle.  |
|               | sec-enforce-vnet-integration         | Network Security                | Restricts storage and database access only within specified Virtual Networks.|
|               | restrict-public-access               | Network Security                | Prevents unauthorized access by ensuring storage accounts are not accessible from public networks.|
| **SQL Server** | Enforce Transparent Data Encryption  | Database Security                | Encrypts data at rest for Azure SQL Databases, maintaining compliance.      |
|               | Restrict Public Access SQL          | Secure Database Access          | Prevents unauthorized public connections to SQL Databases.                 |
|               | Geo-Replication for SQL              | High Availability                | Configures geo-replication across regions for disaster recovery.           |
|               | Automate Database Cleanup           | Cost Management                 | Removes unused databases and containers to reduce costs.                    |
|               | SQL Diagnostic Logging               | Compliance and Auditing         | Logs all database operations and access activity.                           |
|               | List Low Utilized SQL Servers       | Cost Optimization               | Identifies and removes low-utilized SQL servers to save costs.             |
| **Cosmos DB**  | Cost Optimization for Low Utilized  | Cost Efficiency                 | Identifies and optimizes low-utilized Cosmos DB instances to reduce costs.   |
|               | Enforce Geo-Replication             | High Availability                | Ensures geo-replication for improved availability across regions.          |
| **Networking** | Restrict VNet Integration           | Network Security                | Restricts storage and database access only within specified Virtual Networks.|
| **Logging**    | Audit Storage Diagnostics            | Logging and Monitoring          | Enables diagnostic logging for all storage account operations and access.    |
|               | Provisioned DTU/VCores Check       | Cost Control                    | Ensures proper provisioning of DTUs or vCores to meet performance needs.    |

---

## Description of Policies

### **Storage Policies**
- **Enforce Storage Encryption**: Encrypts data stored in Azure Storage Accounts to protect data integrity.
- **Restrict Public Access**: Disables public access, ensuring storage accounts are accessible only within private networks.
- **Configure Firewall Rules**: Sets IP whitelisting to secure access to storage accounts.
- **Enable Soft Delete for Blobs**: Safeguards against accidental data loss by retaining deleted blobs for recovery.
- **Enforce HTTPS Transfer Only**: Forces HTTPS communication to protect data transmission.
- **Cleanup Inactive Blobs**: Reduces costs by automatically removing blobs that haven't been accessed for over 90 days.
- **Lifecycle Management Policies**: Automatically moves data across storage tiers (Hot, Cool, Archive) according to lifecycle and cost policies.

### **SQL Server Policies**
- **Enforce Transparent Data Encryption**: Ensures encryption at rest for SQL databases.
- **Restrict Public Access SQL**: Disallows unauthorized public connections to SQL databases.
- **Geo-Replication for SQL**: Sets up geo-replication to maintain availability across regions.
- **Automate Database Cleanup**: Deletes old databases to reduce unnecessary operational costs.
- **SQL Diagnostic Logging**: Captures logs of all database operations for auditing and traceability.
- **List Low Utilized SQL Servers**: Identifies low-utilized SQL servers and removes them to save costs.

### **Cosmos DB Policies**
- **Cost Optimization for Low Utilized**: Identifies and optimizes underutilized Cosmos DB instances to reduce costs.
- **Enforce Geo-Replication**: Sets up geo-replication for availability across multiple regions.

### **Networking Policies**
- **Restrict VNet Integration**: Ensures all connections to storage/databases are limited to Virtual Networks.

### **Logging Policies**
- **Audit Storage Diagnostics**: Enables diagnostic logging to capture storage account operations and access activity.
- **Provisioned DTU/VCores Check**: Ensures optimal provisioning of DTUs or vCores according to workload requirements.

---

## How to Use These Policies
1. Clone this repository.
2. Install Cloud Custodian CLI or integrate it with your CI/CD pipelines.
3. Deploy these YAML policies to your Azure environment using the Custodian CLI.
4. Customize IP addresses, retention periods, regions, and other parameters as needed for your infrastructure.

---

## Contributing
We welcome contributions! If you have new policies or ideas, submit a pull request or open an issue.

For questions, contact [Your Information].

---

## License
This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).
