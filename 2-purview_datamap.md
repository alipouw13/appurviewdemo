# Overview
The Data Map is the technical arm of the governance side of Purview. Here you connect to and register data sources, manage your collection structure, monitor your data assets and define classification rules.
- Create an up-to-date map of your entire data estate that includes data classification and end-to-end lineage
- Identify where sensitive data is stored in your estate
- Create a secure environment for data consumers to find valuable data
- Generate insights about how your data is stored and used
- Manage access to the data in your estate securely and at scale

# Key Points
- Register your data source at the root if it must be shared across the first level of the collection hierarchy
- Most Policy Enforcment happens at the data product level
- Policies are created for governance domains and for data products
- Automatic policy enforcement is in preview for Azure SQL DBs, Blob Storage accounts and ADLS Gen2 accounts
- Governance domains tend to align to Fabric domains but its not necessarily a 1:1

# Business Value
1. **No cost to register and scan data assets**.
    - Only govererned data assets are billed in the [new Purview PAYGO model](https://learn.microsoft.com/en-us/purview/ms-purview-dg-pricing-announcement) enabling your organization to create a foudation in your Purview Data Map without paying a dime.
3. Centralized Data Discovery and Visibility - unified view of all data assets across on-premises, hybrid, and multi-cloud environments.
    - Value: Banking institutions can break down data silos, enabling efficient discovery of data assets to support customer insights, regulatory reporting, and decision-making.
3. Enhanced Compliance and Risk Management - automatically scan and classify sensitive information, including PII and financial data, aligning with regulatory frameworks like GDPR, CCPA, and Basel III.
    - Value: Banks reduce compliance risk and demonstrate strong governance practices to regulators, auditors, and customers.
4. Improved Data Lineage and Auditability - comprehensive data lineage capabilities allow organizations to track the origin, transformation, and flow of data through their systems.
   - Value: Enhanced auditability simplifies root cause analysis for discrepancies and accelerates response times during audits or investigations.
5. Accelerated Data Access and Insights - automated data classification and tagging enable data stewards and analysts to quickly identify and access the most relevant data for use cases like fraud detection, credit scoring, and portfolio analysis.
    - Value: **Reduces the time spent searching for data** and **accelerates time-to-insight**, **improving operational efficiency**.
6. Supports Data Democratization and Collaboration - the Data Map fosters secure data sharing and collaboration across departments and teams while maintaining control over sensitive data in the colleciton architecture.
    - Value: **Promotes innovation and cross-functional projects** while maintaining strong data governance.

# Permissions
Permissions in the Data Map are captured below.

For each collection, your organization should consider who will require each of the 