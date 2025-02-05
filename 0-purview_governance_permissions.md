# Overview

Assigning in Microsoft Purview can seem like a daunting task. This section aims to walk through the available Purview permissions in the Data Map and the Unified Catalog, map these permissions to Data Management roles and then further to Data Strategy roles specific to your organization.

The Purview permissions sheet in the [reference section tis](https://github.com/alipouw13/appurviewdemo/blob/main/reference) of this repo provides an interactive look on how to begin to configure roles and permissions in Microsoft Purview.

# Microsoft Purview roles

In the Microsoft Purview Data Map and Unified Catalog, roles can be applied at the tenant-level, application-level or the domain-level.

See [here](https://learn.microsoft.com/en-us/purview/governance-roles-permissions#what-data-catalog-permissions-do-i-need) for a list of governance roles.

## Tenant-level roles

Roles applied at the organizational (tenant) level provide admin permissions to the Data Map and the Unified Catalog. These toles are configured by the Purview Admin in the _Roles and scopes > Role Groups_ section of _Settings_ in the Purview Portal (seen below).
![alt](https://github.com/alipouw13/appurviewdemo/blob/main/images/roles-and-scopes.png)

| Role | Description | Permissions | Permission Level |
|------|-------------|-------------|------------------|
| Purview administrator | Create, edit, and delete domains and perform role assignments | Full access to all Purview features | Tenant |
| Data source administrators | Manage data sources and data scans in the Microsoft Purview Data Map | Read and write access to data sources | Tenant (Data Map) |
| Data governance administrator | Grants access to data governance roles within Microsoft Purview | Read and write access over governance domain roles | Tenant (Unified Catalog) |

## Data Map roles

Data map roles provide access to Domains and Collections to manage assets, sources, and other artifacts into a hierarchy for discoverability. The core roles for domains and collections are listed below:

| Role | Permissions |
|------|-------------|
| Domain admin (domain level only) | Assign permissions within a domain and manage its resources. |
| Collection administrator | Add users to roles on collections where they're admins and edit collections, their details, and add subcollections. |
| Data curators | Edit and manage assets, configure custom classifications, create and manage glossary terms, and view data estate insights. |
| Data readers | Read-only access to data assets, classifications, classification rules, collections and glossary terms. |
| Data source administrator | Ability to manage data sources and scans. To create new scan rules, the user must be also granted as either Data reader or Data curator roles. |
| Insights reader | Read-only access to insights reports for collections where the insights reader also has at least the Data reader role|
| Policy author | (domain-level only) Ability to view, update, and delete Microsoft Purview policies through the Data policy app within Microsoft Purview. |
| Workflow administrator | Provides access the workflow authoring page in the Microsoft Purview governance portal, and publish workflows on collections where they have access permissions. Requires at least Data reader permission on a collection to be able to access the Purview governance portal.|

## Unified Catalog roles

Roles in the Unified Catalog applied at the tenant and catalog (application) level, provide a higher level of access to users. Roles applied at the domain-level provide access within a specific governance domain, and should be granted to data experts and business users to read and manage objects within the governance domain.

| Role | Permissions |
|------|-------------|
| Data governance administrator | Delegate all other governance domain permissions, configure data quality scan alerts, and set domain level access policies. |
| Governance domain reader | Ability to read metadata for published governance domains. |
| Governance domain owner | Ability to delegate all other governance domain permissions, configure data quality scan alerts, and set domain level access policies. |
| Data catalog reader | Read published concepts in the catalog across all governance domains as well as all business concepts in the governance domain they are granted access to. |
| Data steward | Create, update, and read artifacts and policies within their governance domain. Can also read artifacts from other governance domains. *Requires Data Map permissions to read those data assets in Data Map. |
| Data product owner | Create, update, and read data products only within their governance domain. Can read artifacts from other domains to build relationships between the concepts. *Requires Data Map permissions to read those data assets in Data Map. |
| Data health owner | Create, update, and read artifacts in health management. |
| Data health reader | Can read artifacts in health management. |
| Data quality steward | Able to use data quality features like data quality rule management, data quality scanning, browsing data profiling and data quality insights, data quality scheduling, job monitoring, configuring threshold and alerts. |
| Data quality reader | Browse all data quality insights and data quality rules definitions. This role can’t run data quality scanning and data profiling jobs, and this role won't have access to data profiling column level insight as column level insight. |
| Data quality metadata reader | Browse data quality insights (except profiling results column level insight), data quality rule definition, and rule level scores. This role won't have access to error records and can't run profiling and DQ scanning job. This is a subrole, to perform this role the individual also needs Governance domain reader and Data Catalog reader roles. |
| Data profile steward | Run data profiling jobs and have access to browse profiling insight details. This role can also browse through all data quality insights and can monitor profiling jobs. This role can’t create rules and can’t run data quality scanning. This is a subrole, to perform this role the individual also needs Governance domain reader and Data Catalog reader roles. |
| Data profile reader | Browse all profiling insights and can drill down the profiling results to browse the statistics in column level. |

# Data management roles

Data management roles refer to a grouping of personas that share similar job functions when it comes to Microsoft Purview. Multiple data strategy roles can be grouped into a single data management role to simplify access management to Microsoft Purview. The 5 core data management roles are defined below. These are the basis for which organizations can create security groups to manage access to appropriate Domains, Collections, Governance Domains and Data Products in your Data Map and Unified Catalog.
![alt](https://github.com/alipouw13/appurviewdemo/blob/main/images/data-management-roles.png)

_Please note that within the Governance persona, there is a Governance Admin and a Data Steward_

# Data strategy roles

Data strategy roles are role unique to your organization. These are roles such as data engineers, IT admins, etc. The list provided below is based on the [Microsoft Cloud Analytics Framework (CAF)](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/scenarios/cloud-scale-analytics/organize-roles-responsibilities) while incorporating Fabric roles as well. The roles below should be adpted to your organization.

| Role | Responsibilities | Data Management Persona |
|------|------------------|-------------------------|
| Data Owner | Responsible for the data's overall governance, ensuring compliance, security, and appropriate access policies within the organization. Responsible for the source data availability and quality. Supports the Data Engineers with ingestion. Approves access. Defines Sensitivity levels. | Publisher |
| Data Product Owner | Oversees the lifecycle of data products, ensuring they meet business needs and align with organizational goals. | Publisher, Producer |
| Data Scientist | Develops predictive models and insights using statistical analysis, machine learning, and data manipulation to solve business problems. | Publisher, Producer |
| ML Engineer | Focuses on designing and deploying machine learning models into production environments. Responsibilities include developing and optimizing ML models, managing ML infrastructure, and ensuring the scalability and reliability of ML solutions. | Publisher, Producer  |
| Data Analyst | Accountable for analyzing data and creating reports. Consulted on data transformations and quality checks. | Producer, Consumer |
| Data Engineer | Builds and maintains scalable data pipelines, transforming and integrating data for analytical and operational use. Ingesting and transforming data. Securing and managing an analytics solution. Monitoring and optimizing an analytics solution. | Shared Services |
| Security Lead | Implements and maintains security tools and controls to protect systems, networks, and data against threats. Defines and implements robust security frameworks for cloud and on-premises systems, protecting data and infrastructure. | Shared Services |
| DevOps/DataOps | Designs and implements scalable and automated data operations frameworks, ensuring efficient data integration, governance, and pipeline reliability across the organization. Maintains automated data workflows, optimizing data pipeline performance, reliability, and collaboration between data engineering and analytics teams. | Shared Services |
| Data Governance Manager | Establishes and enforces policies, standards, and procedures to ensure data quality, security, and compliance across the organization. | Governance |
| Data Steward | Ensures data accuracy, integrity, and proper usage by managing metadata, resolving data issues, and aligning with governance policies taking ownership over domain governance solution. | Governance |
| Data Citizen | Involves using data and analytics tools to make data-driven decisions within the organization. Responsibilities include accessing and analyzing data, creating reports and dashboards, and collaborating with data professionals to gain insights. | Consumer |
| Microsoft 365 Admin | Assigns Roles to Users; purchases, assigns and removes licenses; creates and manages users and groups; and resets passwords. | Shared Services |
| Capacity Admin | Manages workspaces and workloads, and monitors the health of a Fabric capacity. | Shared Services |
| Data Gateway Administrator | Manages gateway data source configuration, credentials, and users assignments. Might also handle gateway software updates (or collaborate with infrastructure team on updates). | Shared Services |
| Workspace Administrator | Manages access and permissions within a specific workspace. Workspace Admins have full administrative rights over all items in the workspace, including databases, tables, and other resources. They can assign roles, manage security settings, and ensure that the workspace operates smoothly. This role is essential for maintaining the security and organization of data within the workspace. | Shared Services |
| Microsoft Fabric Admin | Oversees the entire Microsoft Fabric environment. This role includes managing settings, configurations, and security for the Fabric platform. Fabric Admins have the ability to change tenant settings, enable features like Sensitivity Labels, and manage access to various Fabric services. They can also monitor capacity usage, feature adoption, and asset inventory through the Admin Monitoring Workspace. | Shared Services |
