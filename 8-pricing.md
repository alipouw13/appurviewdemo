# Overview
As of January 6th, 2025 Microsoft Purview has adopted a PAYGO pricing model. This means that you only pay for governed and managed data assets. Governed data assets 

A sample excel sheet for calculating both Unified Catalog and Master Data Management billing is available in the reference section of this repository [here](https://github.com/alipouw13/appurviewdemo/blob/main/reference).

# Unified Catalog Billing
Data assets (eg: tables, views, AI models, semantic models, etc.) that are linked to governance concepts in the product, such as data products and critical data elements, are counted as governed assets. See [here](https://github.com/alipouw13/appurviewdemo/blob/main/3-purview_unifiedcatalog.md) more information here on the Unified Catalog core concepts, including data products and CDEs.

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