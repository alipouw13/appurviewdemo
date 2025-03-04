# Overview

As of January 6th, 2025 Microsoft Purview has adopted a PAYGO pricing model for Data Governance Purview Features. This means that you only pay for governed and managed data assets. Governed data assets are assets that are linked to governance concepts such as data products and critical data elements (CDEs). Managed assets are billed when a customer runs data quality and health management actions on their governed data estate.

A sample excel sheet for calculating both Unified Catalog and Master Data Management billing is available in the reference section of this repository [here](https://github.com/alipouw13/appurviewdemo/blob/main/reference).

# Unified Catalog Billing

Data assets (eg: tables, views, AI models, semantic models, etc.) that are linked to governance concepts, such as data products and CDEs, are counted as governed assets. See [here](https://github.com/alipouw13/appurviewdemo/blob/main/3-purview_unifiedcatalog.md) more information here on the Unified Catalog core concepts, including data products and CDEs.

Key points:

- Data assets scanned into the data map are scanned at no cost. Scanning costs are subsumed by Microsoft Purview.

![alt](https://github.com/alipouw13/appurviewdemo/blob/main/images/data-catalog-pricing.png)

See more information [here](https://learn.microsoft.com/en-us/purview/ms-purview-dg-pricing-announcement#unified-catalog).

# Master Data Management Billing

Data management processing is high value compute for data management workloads. Billing is initiated when a customer runs data quality and health management actions on their governed data assets.

Usage is billed based on the Data Governance Processing Unit (DGPU) pay-as-you-go meters. This compute utilization varies depending on the following dimensions and variability include:

- Data volumes
- Complexity of data management rules and policies (custom vs system generated rules)
- Physical topology of customer data estate (clouds used, on-premise infra, networking, geo locations and residency requirements)

One DGPU = 60 minutes of data management capacity (compute, storage, network I/O), metered and billed at time expended.

There are 3 SKUs available for Data health management - each increase in price provides increased speed and parallelism. By default, the _Basic_ SKU is set as default.

- Basic : $15 per processing unit
- Standard : $60 per processing unit
- Advanced : $240 per processing unit

See below for a snapshot of pricing calculator.

![alt](https://github.com/alipouw13/appurviewdemo/blob/main/images/mdm-pricing.png)

See more information [here](https://learn.microsoft.com/en-us/purview/ms-purview-dg-pricing-announcement#data-management).

# Data Security Solutions for non-M365 Data Billing

Microsoft Purview Information Protection and Data Loss Prevention are billed based upon the number of assets protected (tables, files, resource sets, etc). In addition, DLP or protection policies can then be applied to these assets to control how they are handled, shared, and protected. These policies can enforce actions like access control, auditing, and end user notifications for the monitoring of this sensitive information. 

Microsoft Purview Insider Risk Management is billed based on the data security processing unit (DSPU). Insider Risk Management processes activities corresponding to the indicators selected in the policies to generate insights, alerts and cases.
  - Information Protection & Data Loss Prevention: Pay as you go 0.0165/asset/day (~$0.50 per month)
  - Insider Risk Management: Pay as you go $25 per DS processing unit

# Data Security & Compliance Solutions for M365 Data Billing

## Microsoft 365 E3 License

Microsoft 365 E3 ($33.75 pupm) includes core risk and compliance solutions:
- Information Protection 
- Data Loss Prevention for Exchange Online, SharePoint Online & OneDrive for Business
- Data Lifecycle Management 
- Compliance Manager
- eDiscovery
- Audit

Advanced risk and compliance solutions can be added to Microsoft 365 E3 with the purchase of the ME5 Compliance add-on or one of the Microsoft 365 E5 Compliance mini-suites (ME5 Information Protection & Governance, ME5 Insider Risk Management and ME5 eDiscovery & Audit).

## Microsoft 365 E5 License

Microsoft 365 E5 ($54.75 pupm) includes everything in Microsoft 365 E3, plus the advanced Microsoft Purview risk and compliance solutions found in Microsoft 365 E5 Compliance. 

Microsoft 365 E5 Compliance add-on ($12 pupm) provides advanced risk and compliance solutions comprised of these 3 individual mini-suite add-ons:

1. Microsoft 365 E5 Information Protection & Governance add-on ($7 pupm)

  - Information Protection 
  - Data Lifecycle Management
  - Records Management
  - Data Loss Prevention

2. Microsoft 365 E5 Insider Risk Management add-on ($6 pupm)

  - Insider Risk Management
  - Communication Compliance

3. Microsoft 365 E5 eDiscovery & Audit add-on ($6 pupm)

  - eDiscovery (Premium)
  - Audit (Premium)
