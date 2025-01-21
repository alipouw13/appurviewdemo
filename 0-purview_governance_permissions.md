# Overview
Assigning in Microsoft Purview can seem like a daunting task. This section aims to walk thrugh the available Purview permissions in the Data Map and the Unified Catalog, map these permissions to Data Management roles and then further to Data Strategy roles specific to your organization.

# Microsoft Purview roles
In the Microsoft Purview Data Map and Unified Catalog, roles can be applied at the tenant-level, application-level or the domain-level.


See [here](https://learn.microsoft.com/en-us/purview/governance-roles-permissions#what-data-catalog-permissions-do-i-need) for a list of governance roles

## Tenant-level roles
Roles applied at the organizational (tenant) level provide admin permissions to the Data Map and the Unified Catalog. These toles are configured by the Purview Admin in the _Roles and scopes > Role Groups_ section of _Settings_ in the Purview Portal (seen below).
![alt](https://github.com/alipouw13/appurviewdemo/blob/main/images/roles-and-scopes.png)

| Role | Description | Permissions | Permission Level |
|------|-------------|-------------|------------------|
| Purview administrator | Create, edit, and delete domains and perform role assignments | Full access to all Purview features | Tenant-level |
| Data source administrators | Manage data sources and data scans in the Microsoft Purview Data Map | Read and write access to data sources | Data Map |
| Data governance administrator | Grants access to data governance roles within Microsoft Purview | Read and write access over governance domain roles | Unified Catalog |


## Data Map roles
Data map roles provide access to Domains and Collections to manage assets, sources, and other artifacts into a hierarchy for discoverability. The core roles for domains and collections are listed below:

| Role | Description | Permissions |
|------|-------------|-------------|
| Domain admin (domain level only) | Administers specific domains | Create domains and assign roles to specific domains |
| Collection administrator | Administers collections | Full access to edit and manage collections |
| Data curators | Curates data within collections | Edit and manage assets, configure custom classifications, create and manage glossary terms, and view data estate insights. |
| Data readers | Reads data within collections | Read-only access to data assets, classifications, classification rules, collections and glossary terms. |
| Data source administrator | Administers data sources | Ability to manage data sources and scans. To create new scan rules, the user must be also granted as either Data reader or Data curator roles. |
| Insights reader | Reads insights report information | Read-only access to insights reports for collections where the insights reader also has at least the Data reader role|
| Policy author | Authors policies | (domain-level only) Ability to view, update, and delete Microsoft Purview policies through the Data policy app within Microsoft Purview. |
| Workflow administrator | Administers workflows | Provides access the workflow authoring page in the Microsoft Purview governance portal, and publish workflows on collections where they have access permissions. Requires at least Data reader permission on a collection to be able to access the Purview governance portal.|


## Unified Catalog roles
Roles in the Unified Catalog applied at the tenant and catalog (applicaiton) level, provide a higher level of access to users. Roles applied at the domain-level provide access within a specific governance domain, and should be granted to data experts and business users to read and manage objects within the governance domain.

| Role | Description | Permissions |
|------|-------------|-------------|
| Data governance administrator | Grants access to data governance roles within Microsoft Purview  | Read and write access over governance domain roles |
| Governance domain reader | Reads data governance domain information | Read-only access to governance domains |
| Governance domain owner | Owns and manages governance domains | Full access to specific governance domains |
| Governance domain curator | Curates data within governance domains | Edit access to specific governance domains |
| Data catalog reader | Reads data catalog entries | Read-only access to data catalog |
| Data steward | Manages data assets and ensures data quality | Edit access to data assets |
| Data product owner | Owns data products and manages their lifecycle | Full access to data products |
| Data health owner | Oversees data health and quality | Full access to data health features |
| Data health reader | Reads data health information | Read-only access to data health features |
| Data quality steward | Ensures data quality and compliance | Edit access to data quality features |
| Data quality reader | Reads data quality information | Read-only access to data quality features |
| Data quality metadata reader | Reads metadata related to data quality | Read-only access to data quality metadata |
| Data profile steward | Manages data profiling activities | Edit access to data profiling features |
| Data profile reader | Reads data profiling information | Read-only access to data profiling features |


# Data Management roles
Data management roles refer to a grouping of personas that share similar job functions when it comes to Microsoft Purview. Multiple data strategy roles can be grouped into a single data management role to simplify access management to Microsoft Purview. The 5 core data management roles are defined below. These are the basis for which organizations can create security groups to manage access to appropriate Domains, Collections, Governance Domains and Data Products in your Data Map and Unified Catalog.
![alt](https://github.com/alipouw13/appurviewdemo/blob/main/images/data-management-roles.png)

# Data strategy roles
Data strategy roles are role unique to your organization. These are roles such as data engineers, IT admins, etc. The list provided below id taken from the Microsoft Cloud Analytics Framework (CAF) and should be adpted to your organizaiton.
