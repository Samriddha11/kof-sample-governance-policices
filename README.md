# Azure Cloud Custodian Policies

This repository contains a collection of **Cloud Custodian** policies to manage **Azure resources**, including Storage Accounts, SQL Servers, and Cosmos DB. These policies focus on enhancing security, optimizing costs, ensuring compliance, and maintaining operational efficiency.

---

## Table of Policies

| **Policy Name**                      | **Objective**                    | **Description**                                                                 |
|--------------------------------------|---------------------------------|-----------------------------------------------------------------------------|
| **Enforce Storage Encryption**     | Ensure Data at Rest Encryption  | Ensures encryption at rest for all data in Azure Storage Accounts.            |
| **Restrict Public Access**         | Secure Storage Account Access  | Disables public access to storage accounts, allowing only private access.   |
| **Configure Firewall Rules**       | IP Access Control               | Allows access only from specified IP addresses to secure storage accounts.   |
| **Enable Soft Delete for Blobs**   | Prevent Data Loss               | Protects against accidental deletions by enabling soft delete on blobs.      |
| **Enforce HTTPS Transfer Only**    | Secure Data Transmission        | Forces communication with storage accounts to use HTTPS.                    |
| **Cleanup Inactive Blobs**        | Optimize Storage Costs          | Automatically deletes blobs that have not been accessed for more than 90 days. |
| **Lifecycle Management Policies**   | Cost Optimization               | Moves data across storage tiers (Hot, Cool, Archive) based on age and cost.  |
| **Audit Storage Diagnostics**      | Logging and Monitoring          | Enables logging to capture storage account operations and access activity.    |
| **VNet Integration Enforcement**    | Network Security                | Restricts access to storage accounts within specified Virtual Networks.       |
| **Enforce Transparent Data Encryption (SQL)** | Database Security | Ensures encryption at rest is enabled on Azure SQL Databases.                |
| **Restrict Public Access SQL**     | Secure Database Access          | Prevents unauthorized access by disallowing public connections to SQL.      |
| **Geo-Replication for SQL**        | High Availability                | Configures geo-replication to ensure database availability across regions.   |
| **Automate Database Cleanup**     | Cost Management                 | Automatically removes old databases or unused SQL containers to reduce costs.  |
| **SQL Diagnostic Logging**         | Compliance and Auditing         | Ensures diagnostic logs capture all operations on SQL databases.             |
| **Provisioned DTU/VCores Check** | Cost Control                    | Ensures proper provisioning of DTUs or vCores to meet performance needs.     |
| **Storage Service Lifecycle Policy** | Data Tier Management | Manages data across storage tiers automatically to optimize costs.          |

---

## Description of Policies

### 1. **Enforce Storage Encryption**
- Encrypts data stored in Azure Storage Accounts to protect against data breaches and compliance issues.

### 2. **Restrict Public Access**
- Ensures storage accounts do not have public access, enhancing network security.

### 3. **Configure Firewall Rules**
- Limits access only to specified IP ranges, ensuring that only trusted sources connect to storage accounts.

### 4. **Enable Soft Delete for Blobs**
- Provides protection against accidental deletions by retaining deleted blobs for a specified retention period.

### 5. **Enforce HTTPS Transfer Only**
- Ensures communication with storage accounts is only via HTTPS, safeguarding data in transit.

### 6. **Cleanup Inactive Blobs**
- Reduces storage costs by automatically deleting blobs that haven't been accessed for over 90 days.

### 7. **Lifecycle Management Policies**
- Automates the movement of data to different storage tiers (Hot, Cool, Archive) according to lifecycle and cost policies.

### 8. **Audit Storage Diagnostics**
- Enables comprehensive logging and auditing to monitor read/write activities and access operations.

### 9. **VNet Integration Enforcement**
- Secures storage accounts by ensuring that access is only available within specified Virtual Networks.

### 10. **Transparent Data Encryption for SQL**
- Encrypts data at rest for Azure SQL Databases, maintaining database integrity and compliance.

### 11. **Restrict Public Access SQL**
- Prevents unauthorized access by disabling public connections to Azure SQL Databases.

### 12. **Geo-Replication for SQL**
- Configures geo-replication for high availability and disaster recovery across multiple regions.

### 13. **Automate Database Cleanup**
- Reduces operational costs by cleaning up databases and containers that are no longer in use.

### 14. **SQL Diagnostic Logging**
- Captures all database activities, operations, and access logs to ensure compliance and traceability.

### 15. **Provisioned DTU/VCores Check**
- Maintains performance and cost efficiency by ensuring proper provisioning of DTUs or vCores.

### 16. **Storage Service Lifecycle Policy**
- Automatically optimizes storage costs by managing data across storage tiers according to lifecycle requirements.

---

## How to Use These Policies
1. Clone this repository.
2. Deploy Cloud Custodian CLI or integrate it with your CI/CD pipeline.
3. Use the provided YAML policy files with the Custodian CLI to apply these policies to your Azure environment.
4. Customize the IP addresses, retention days, regions, and other parameters as needed for your specific environment.

---

## Contributing
We welcome contributions! If you have additional policies or suggestions, please submit a pull request or open an issue.

For questions and support, reach out to [Your Contact Information].

---

## License
This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).
