# Cosmos DB Governance Policies

This repository contains a set of governance policies targeting Azure Cosmos DB resources. Each policy leverages filters and metrics to identify opportunities for cost savings, improved resource tagging, right-sizing throughput, and other best practices.

The table below provides an overview of all Cosmos DB policies, their purpose, and the related resource.

| Policy Name                          | Resource          | Description                                                                                                                                              |
|--------------------------------------|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| cosmosdb-underutilized               | azure.cosmosdb    | Find Cosmos DB accounts with high provisioned throughput but low actual usage, highlighting opportunities to reduce RU capacity and lower costs.         |
| cosmosdb-unused                      | azure.cosmosdb    | Check for zero request units over the past week to identify unused Cosmos DB accounts that may be candidates for deprovisioning or cost optimization.     |
| cosmosdb-analytical-store-not-used   | azure.cosmosdb    | Identify accounts enabled with analytical store but with very low request units, prompting a review to disable or reconfigure to save costs.             |
| cosmosdb-low-change-continuous-backup| azure.cosmosdb    | Find accounts on continuous backup with minimal write activity, suggesting switching to periodic backup for cost reduction.                              |
| cosmosdb-missing-cost-tags           | azure.cosmosdb    | Flag Cosmos DB accounts missing cost-related tags, encouraging better cost allocation and transparency.                                                  |
| cosmosdb-inactive                    | azure.cosmosdb    | Identify Cosmos DB accounts with low total requests over the last 72 hours, indicating potentially inactive or underutilized resources.                  |
| cosmosdb-not-using-autoscale         | azure.cosmosdb    | Find Cosmos DB accounts not leveraging autoscale despite low usage, prompting consideration to enable autoscale and optimize cost.                       |
| list-low-utilised-cosmodb            | azure.cosmosdb    | List all Cosmos DB accounts with low utilization (based on low request counts in the last 72 hours) for potential cost optimization actions.              |
| restrict-cross-region-write          | azure.cosmosdb    | Restrict cross-region writes by ensuring there are no write regions set and enforcing a specific region if needed.                                       |
| cosmosdb-multi-region-low-usage      | azure.cosmosdb    | Identify multi-region Cosmos DB accounts with low request units, prompting reviews to remove unnecessary regions and reduce costs.                       |

---

## Additional Policies for Azure SQL Databases and SQL Servers

In addition to the Cosmos DB policies, this repository also includes policies for Azure SQL Databases and SQL Servers. These policies focus on identifying idle or underutilized databases, encouraging the use of cost-effective tiers, ensuring proper tagging, and prompting adjustments to retention policies.

| Policy Name                             | Resource            | Description                                                                                                                   |
|-----------------------------------------|---------------------|-------------------------------------------------------------------------------------------------------------------------------|
| sql-database-idle                       | azure.sql-database  | Monitors metrics over the past 72 hours, identifies databases with zero usage, and suggests deleting or scaling down.         |
| list-low-utilised-sql-server            | azure.sqlserver     | Lists SQL servers with less than 10% average DTU consumption over the last 72 hours to find opportunities for cost reduction.  |
| sql-database-excessive-backup-retention | azure.sql-database  | Checks if long-term retention exceeds 24 months, notifies admin to consider shorter retention for cost savings.               |
| sql-database-not-serverless             | azure.sql-database  | Identifies databases not in a serverless tier that have low CPU usage, prompting a review to consider moving to serverless.    |
| sql-database-overprovisioned            | azure.sql-database  | Targets databases on costly tiers with very low CPU usage, suggesting scaling down to a cheaper tier for cost optimization.    |
| sql-database-missing-cost-tags          | azure.sql-database  | Flags databases without important cost-related tags, encouraging tagging to improve cost tracking and accountability.         |

---

## Additional Policies for Azure Storage Accounts

This repository also includes policies for Azure Storage accounts. These policies target opportunities to move data to cheaper tiers, downgrade premium tiers when not needed, and identify storage accounts that appear unused.

| Policy Name                         | Resource       | Description                                                                                                                                      |
|-------------------------------------|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| storage-accounts-hot-tier-underutilized | azure.storage | Finds storage accounts with large data volumes in the hot tier but very low read access, suggesting a move to cooler or archive tiers to save cost. |
| storage-premium-overprovisioned     | azure.storage  | Targets premium-tier storage accounts with very low transaction counts, recommending downgrading to Standard tiers.                              |
| storage-unused                      | azure.storage  | Checks for no transactions over the last 7 days, prompting consideration of deleting the storage account or archiving its data.                  |

**Note:** The policies are defined in YAML files within this repository. Each policy includes resource targets, filters, and in some cases, actions to take. Adjust the thresholds and filtering criteria as needed to align with your organizational standards and cost optimization goals.
