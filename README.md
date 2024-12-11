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
| **SQL Server** | sec-enforce-tde-on-sql  | Database Security                | Encrypts data at rest for Azure SQL Databases, maintaining compliance.      |
|               | sql-firewall-rules          | Secure Database Access          | Prevents unauthorized public connections to SQL Databases.                 |
|               | rel-enable-sql-geo-replication              | High Availability                | Configures geo-replication across regions for disaster recovery.           |
|               | cost-cleanup-inactive-sql-databases          | Cost Management                 | Removes unused databases and containers to reduce costs.                    |
|               | sec-audit-sql-diagnostics               | Compliance and Auditing         | Logs all database operations and access activity.                           |
|               | cost-list-low-utilised-sql-server       | Cost Optimization               | Identifies and removes low-utilized SQL servers to save costs.             |
|               | cost-enforce-provisioned-dtu-limits     | Cost Control                    | Ensures proper provisioning of DTUs or vCores to meet performance needs.    |
|               | sql-vnet-access-restriction         | Network Security                | Restricts database access only within specified Virtual Networks.|
|               | op-enforce-backup-retention         | Prevent Data Loss               | Protects critical data by ensuring recovery is possible over extended periods.|
| **Cosmos DB**  | cost-list-low-utilised-cosmodb  | Cost Efficiency                 | Identifies and optimizes low-utilized Cosmos DB instances to reduce costs.   |
|               | rel-enforce-cosmosdb-backups-grs            | High Availability                | GRS ensures that data is available even during regional outages.          |
|               | cost-cleanup-inactive-cosmosdb-containers           | Cost Optimization          | Reduces costs and clutter by removing unused containers    |
|               | sec-audit-cosmosdb-logging      | Compliance and Auditing                    | Comprehensive logging ensures visibility into activities and operations on Cosmos DB.|
|               |sec-cosmosdb-firewall-rules    | Secure Database Access          | Prevents unauthorized public connections to SQL Databases.                 |
|               |sec-enforce-cosmosdb-encryption          | Data at Rest Encryption         | Ensures encryption at rest for all data in CosmosDB           |
|               |perf-enforce-provisioned-throughput           | Performance Optimization                              | Helps maintain predictable costs and better performance by ensuring provisioning meets workload requirements.|
|               |cost-restrict-cross-region-write              |Cost and Performance Optimization |Minimizes latency and operational complexity by controlling write operations in a preferred region.

---

## How to Use These Policies
1. Clone this repository.
2. Create these policies in Harness Asset Governance
3. Dry Run these policies on selected non-production Azure Accounts
4. Customize IP addresses, retention periods, regions, and other parameters as needed for your infrastructure.

---

## Contributing
We welcome contributions! If you have new policies or ideas, submit a pull request or open an issue.

For questions, contact [Your Information].

---

## License
This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).
