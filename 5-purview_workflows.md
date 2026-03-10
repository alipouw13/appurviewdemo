# Overview

Microsoft Purview Workflows in the Unified Catalog provide a centralized, automated way to manage approval scenarios in your data governance solution. Workflows are automated, repeatable sets of actions or business processes that streamline operations and ensure consistent governance practices across your organization.

Workflows enable organizations to track changes, enforce policy compliance, and ensure quality data across their data landscape by automating approval processes for key governance activities.

## Workflow Types

Microsoft Purview Unified Catalog supports two primary workflow types:

### 1. Data Product Access Workflows

Automate the approval process for granting access to data products. These workflows:
- Can be applied to a **governance domain** or a **single data product**
- Enable self-service data access with proper governance controls
- Provide customizable approval chains to ensure the right stakeholders review access requests
- Integrate with existing access policies and data product configurations

**Key Use Cases:**
- Approving user requests to access sensitive data products
- Implementing multi-stage approval for high-risk data access
- Automating access provisioning after approval
- Maintaining audit trails of access requests and approvals

### 2. Publication Workflows

Automate the approval process for publishing data products and glossary terms. These workflows:
- Can **only be applied at the governance domain level**
- Ensure quality control before business concepts become available to users
- Enable data stewards to review and approve content before publication
- Maintain consistency and accuracy across the catalog

**Key Use Cases:**
- Reviewing and approving new data products before they're discoverable
- Validating glossary terms and business definitions
- Ensuring data products meet quality standards before publication
- Coordinating cross-functional review processes

> **Note**: Workflows are set up directly within Unified Catalog and go through a requests and approvals interface with customizable configuration options.

## Workflow Scope

| Workflow Type | Scope Options | Who Can Create |
|---------------|---------------|----------------|
| Data Product Access | Governance domain or individual data product | Data Product Owner |
| Publication | Governance domain only | Governance Domain Creator |

# Business Value

1. **Streamlined Data Governance Processes** - automate approval processes for data access and publication, ensuring consistent and efficient governance operations.
    - Value: Reduces manual effort and accelerates governance actions, enabling organizations to focus on higher-value activities while maintaining compliance.
2. **Improved Collaboration Across Teams** - enable structured collaboration between data stewards, compliance officers, data analysts and data owners by defining clear responsibilities and approval workflows.
    - Value: Enhances efficiency and transparency in cross-functional projects, such as ensuring data quality for risk management or regulatory reporting.
3. **Customizable Workflows for Organizational Needs** - tailor workflows to address specific scenarios, such as handling sensitive data access, validating data product quality, or managing glossary term approvals.
    - Value: Aligns governance processes with unique industry requirements, ensuring a fit-for-purpose solution that meets operational and regulatory demands.
4. **Auditability and Transparency** - provides an end-to-end view of workflow history, including approvals, escalations, and actions taken, supporting accountability and transparency.
    - Value: Simplifies audits and strengthens compliance by offering a clear record of governance activities.
5. **Accelerated Decision-Making** - automated notifications and task assignments ensure that the right stakeholders are informed and involved at the right time.
    - Value: Reduces delays in critical decisions, such as granting data access for time-sensitive analyses, enabling faster responses to business needs.
6. **Self-Service with Governance** - enables users to request access to data products through a governed process while maintaining security and compliance.
    - Value: Balances data democratization with proper oversight, allowing business users to access needed data without compromising governance standards.

# Permissions

To create and manage workflows in Unified Catalog, users need the following permissions:

| Workflow Type | Required Role | Permission Level |
|---------------|---------------|------------------|
| Publication Workflows | Governance Domain Creator | Governance Domain |
| Data Product Access Workflows | Data Product Owner | Governance Domain / Data Product |

Learn more about [Unified Catalog roles and permissions](https://learn.microsoft.com/purview/data-governance-roles-permissions#unified-catalog-roles).

# Getting Started

To set up workflows in your Unified Catalog:

1. **Plan your approval process** - Determine who needs to approve access requests or publications
2. **Configure workflows** - Set up workflows at the appropriate scope (governance domain or data product)
3. **Define approval chains** - Specify single or multi-stage approvals based on your governance requirements
4. **Enable notifications** - Configure automated alerts to keep stakeholders informed
5. **Monitor and optimize** - Track workflow performance through the requests and approvals interface

For detailed implementation guidance, see [Create workflows in Unified Catalog](https://learn.microsoft.com/purview/unified-catalog-workflows).
