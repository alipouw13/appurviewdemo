# Overview
Data Policy is where you can configure and manage various data policies for your organization. You are able to configure and manage the following data policies:
- [Data owner policies](https://learn.microsoft.com/en-us/purview/legacy/concept-policies-data-owner) - a set of policy statements such that when a policy is published to one or more data systems under Microsoft Purview’s governance, it's then enforced.
- [Self-service access policies](https://learn.microsoft.com/en-us/purview/legacy/concept-self-service-data-access-policy) -  allows the data consumer (Unified Catalog reader) to request access to data when browsing or searching for data. The asset must have Policy enforcement enabled, and the self-service access workflow must aslo be enabled.
- [DevOps policies](https://learn.microsoft.com/en-us/purview/legacy/concept-policies-devops) - a type of Microsoft Purview acess policies that grant access to database system metadata instead of user data.
- [Protection policies](https://learn.microsoft.com/en-us/purview/how-to-create-protection-policy?tabs=azure-sources) - enable organizations to automatically protect sensitive data across data sources

## Core Concepts
Below are the data policy core concepts.
- Data owner policies are in preview
- Self-service access policies are in preview
- Hierarchical enforcement of policies (data access and DevOps) applies - if a policy is applied at the parent level, all children will inherit this policy
- DevOps policies can only be created after the data source is registered in Microsoft Purview with the Data policy enforcement option turned on
- DevOps policies only grant access. They don't deny access.
- Self-service data access policy is only supported when [Data policy enforcement is enabled](https://learn.microsoft.com/en-us/purview/legacy/how-to-enable-data-policy-enforcement#prerequisites)
- Protection policies are limited ot Azure SQL Databases, Azure blob storage, ADLS Gen2 and Microsoft Fabric.
- Protection policies require one of the Microsoft 365 E5 licenses

# Business Value
1. **Simplified Governance Across Hybrid Environments**- centralized management of access and data governance policies across on-premises, hybrid, and multi-cloud environments.
    - Value: Reduces operational complexity and ensures consistency in governance practices across all banking data sources.
2. **Automated Compliance with Regulatory Requirements** - tailor policies to enforce compliance with industry regulations like GDPR, CCPA, PCI DSS, and Basel III.
    - Value: Minimizes the risk of regulatory violations, reduces manual compliance efforts, and ensures adherence to evolving regulatory requirements.
3. **Granular Data Access** - Enables fine-grained access controls, allowing organizations to define who can access specific data assets and how they can be used.
    - Value: Protects sensitive financial and customer data, mitigates the risk of data breaches, and ensures that only authorized personnel can access critical information.
4. **Enhanced Data Security and Risk Mitigation** - by applying consistent policies, Data Policy feature ensures data security and prevents unauthorized use or sharing.
    - Value: Safeguards sensitive banking data, such as personally identifiable information (PII) and transaction records, reducing the risk of reputational damage or financial loss from breaches.
5. **Enhanced Operational Efficiency** - policies can be defined once and applied at scale across multiple data assets and environments, with built-in auditing and monitoring to ensure compliance.
    - Value: Reduces the administrative burden on IT and governance teams, allowing them to focus on strategic initiatives instead of manual policy management.

# Permissions
| **Role**                                                                 | **Applicable Data Policy Concept** | **Details**                                                              |
|-----------------------------------------------------------------------|------------------------------------|-----------------------------------------------------| 
| **Policy author**                               | All  | Must have Policy Admin permissions at the domain level. Can create, update, and delete DevOps and Data Owner policies. Can delete self-service access policies.                                            |
| **IAM Owner or both IAM contributor and IAM user access admin**        | All                        | Required on the data source on which data policy enforcement is applied.                            |
| **Workflow admin**                                               | Self-service access policies                       | Must be a Workflow admin to map a self-service data access workflow to a collection.                         |
| **Data Source Admin**                                              | All                        | Required to enable data policy enforcement.                              |
| **[Information protection](https://learn.microsoft.com/en-us/purview/how-to-create-protection-policy-azure-sources#users-and-permissions) role**           | Protection policies       | Required to configure protection policies.           |
