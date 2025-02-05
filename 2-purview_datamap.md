# Overview

The Data Map is the technical arm of the governance side of Purview. Here you connect to and register data sources, manage your collection structure, monitor your data assets and define classification rules.

- Create an up-to-date map of your entire data estate that includes data classification and end-to-end lineage
- Identify where sensitive data is stored in your estate
- Create a secure environment for data consumers to find valuable data
- Generate insights about how your data is stored and used
- Manage access to the data in your estate securely and at scale

## Core concepts

Below are core purview Data Map concepts

| Concept             | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| Data domains        | Logical groupings of data assets that share common policies, security requirements, and characteristics.         |
| Collections         | Hierarchical groupings to organize data sources and assets. Groupings are generally by business unit, geography, environment or project/application               |
| Register a source   | The process of connecting a data source to the Purview Data Map.            |
| Scan a source       | The action of scanning a registered data source into the Data map to discover its metadata and further group to serve to end users in the Unified catalog.   |
| Classifications     | Labels applied to data assets to categorize and protect sensitive data.     |
| Scan rule sets      | Configurations that define how and how much data sources should be scanned and classified.|

# Key points

- Register your data source at the root domain if it must be shared across the first level of the collection hierarchy
- Policies are created for governance domains and for data products
- Most policy enforcement happens at the data product level
- Automatic policy enforcement on data sources is in preview for Azure SQL DBs, Blob Storage accounts, and ADLS Gen2 accounts
- Governance domains tend to align to Fabric domains but it is not necessarily a 1:1 mapping

# Business Value

1. **No cost to register and scan data assets**.
    - Only governed data assets are billed in the [new Purview PAYGO model](https://learn.microsoft.com/en-us/purview/ms-purview-dg-pricing-announcement) enabling your organization to create a foundation in your Purview Data Map without paying a dime.
3. **Centralized Data Discovery and Visibility** - unified view of all data assets across on-premises, hybrid, and multi-cloud environments.
    - Value: Banking institutions can break down data silos, enabling efficient discovery of data assets to support customer insights, regulatory reporting, and decision-making.
3. **Enhanced Compliance and Risk Management** - automatically scan and classify sensitive information, including PII and financial data, aligning with regulatory frameworks like GDPR, CCPA, and Basel III.
    - Value: Banks reduce compliance risk and demonstrate strong governance practices to regulators, auditors, and customers.
4. **Improved Data Lineage and Auditability** - comprehensive data lineage capabilities allow organizations to track the origin, transformation, and flow of data through their systems.
   - Value: Enhanced auditability simplifies root cause analysis for discrepancies and accelerates response times during audits or investigations.
5. **Accelerated Data Access and Insights** - automated data classification and tagging enable data stewards and analysts to quickly identify and access the most relevant data for use cases like fraud detection, credit scoring, and portfolio analysis.
    - Value: **Reduces the time spent searching for data** and **accelerates time-to-insight**, **improving operational efficiency**.
6. **Supports Data Democratization and Collaboration** - the Data Map fosters secure data sharing and collaboration across departments and teams while maintaining control over sensitive data in the collection architecture.
    - Value: **Promotes innovation and cross-functional projects** while maintaining strong data governance.

# Permissions

Permissions mappings for data management roles to Purview Data Map roles are captured below. Please use this as a guide to define the roles / security groups for the data map. Keep in mind that each level of the collection hierarchy should  

![alt](https://github.com/alipouw13/appurviewdemo/blob/main/images/dm-role-mapping.png)

For each collection, your organization should consider who will require each of the defined permissions above. See the [Purview Governance Permissions doc](https://github.com/alipouw13/appurviewdemo/blob/main/0-purview_governance_permissions.md) for more information and relevant links.
