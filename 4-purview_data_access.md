# Overview

Data Product Access Policies in Microsoft Purview Unified Catalog enable governed, self-service access to data products. Through workflow-based approvals and attestations, organizations can balance data democratization with proper oversight and compliance.

Access to a data product in Unified Catalog grants users permissions to both the data product and the underlying data assets within the data product. This approach integrates business context with technical access management. It does not grant access to the physical data asset.

## How Data Product Access Works

When users browse or search the Unified Catalog and find data products they need, they can request access directly through the catalog interface. Access requests flow through configurable approval workflows that can include:

- **Manager Approval**: Automatic approval routing to the requestor's manager in Microsoft Entra ID
- **Privacy & Compliance Review**: Designated privacy reviewers evaluate requests for compliance
- **Access Request Approvers**: Data product owners or designated approvers review and approve access
- **Access Providers**: Optional tier to manually provision access to underlying data assets

### Inherited Policies

Policies set at different levels aggregate to provide comprehensive governance:

- **Governance Domain Policies**: Apply to all data products within the domain
- **Glossary Term Policies**: Apply when terms are associated with data products
- **Critical Data Element Policies**: Apply when CDEs are associated with data products
- **Data Product Policies**: Specific policies configured for individual data products

When a user requests access, they see an aggregated view of all applicable policies and must attest to all required conditions.

## Core Concepts

### Policy Configuration

Data product access policies define:

1. **Permitted Usage Purposes**: Authorized business reasons for accessing the data
2. **Approval Requirements**: Which tiers of approval are required (manager, privacy, access approver, access provider)
3. **Attestations**: Terms and conditions users must agree to, including:
   - No-copy attestations
   - Terms of use
   - Custom attestations with supporting documentation
4. **Access Request Approvers**: Users or groups who approve access requests
5. **Access Providers**: Optional users who manually provision access to underlying data assets

### Tiered Approval Workflow

Access requests follow a sequential approval process:

1. **Manager Approval** (if configured) - Requestor's Microsoft Entra ID manager reviews first
2. **Privacy Review** (if configured) - Privacy reviewer named by requestor evaluates compliance
3. **Access Request Approver** - Data product owners or designated approvers review and approve
4. **Access Provider** (if configured) - Designated users manually provision access to data assets

The request proceeds to each tier only after the previous tier approves. Any denial stops the workflow and notifies the requestor.

### Important Considerations

> **Note**: Manual provisioning is required. The access request workflow doesn't automatically grant permissions to underlying physical data assets. Approvers or access providers must manually configure access through the data source's access management system (Azure IAM, Fabric workspace permissions, etc.).

- **Attestations**: The system doesn't enforce attestations like no-copy policies; users attest they'll follow these policies during the request process
- **Manual Access Granting**: Approvers must provide access to individual data assets as part of the approval process or designate an access provider to do so
- **Request Tracking**: All request statuses and actions are tracked and visible to requestors through the "My data access" tab
- **Email Notifications**: Approvers receive email notifications and can approve directly from the email

## Business Value

1. **Self-Service Data Access with Governance** - enable data consumers to discover and request access to data products while maintaining proper oversight and compliance controls.
    - Value: Accelerates time-to-insight while ensuring security, compliance, and proper usage of sensitive data.
2. **Workflow-Based Approval Process** - configure multi-tiered approval workflows that route requests to managers, privacy reviewers, and data owners based on sensitivity and compliance requirements.
    - Value: Reduces administrative burden while ensuring appropriate stakeholders review and approve access based on business context.
3. **Attestation and Compliance Tracking** - require users to attest to terms of use, no-copy policies, and custom compliance requirements before accessing data.
    - Value: Provides audit trails for compliance reporting and ensures users acknowledge their responsibilities.
4. **Inherited Policy Aggregation** - policies defined at governance domain, glossary term, and critical data element levels automatically apply to relevant data products.
    - Value: Ensures consistent governance across related data products without duplicating policy configuration.
5. **Business Context for Access Decisions** - access requests include business justification through usage purposes, enabling approvers to make informed decisions.
    - Value: Connects technical access management with business needs and helps track how data is being used across the organization.
6. **Integrated Discovery and Access** - users discover, understand, and request access to data products in a single experience within the Unified Catalog.
    - Value: Simplifies the data access journey and reduces friction for data consumers while maintaining governance controls.

# Permissions

To work with data product access policies in Microsoft Purview Unified Catalog, users need specific roles:

| Role | Level | Permissions |
|------|-------|-------------|
| **Data Product Owner** | Governance Domain | Configure access policies for specific data products. Approve access requests. Manually provision access to data assets. |
| **Data Steward** | Governance Domain | Create, update, and read artifacts and policies within their governance domain. Can also read artifacts from other governance domains. Configure access policies on glossary terms and critical data elements. |
| **Governance Domain Owner** | Governance Domain | Configure domain-level access policies that apply to all data products in the domain. Delegate permissions to data stewards and data product owners. |
| **Governance Domain Creator** | Catalog | Create governance domains and configure initial access policies. |
| **Global Catalog Reader** | Catalog | Browse and search published data products across all governance domains. Request access to data products. |
| **Local Catalog Reader** | Governance Domain | Browse and search published data products only within assigned governance domains. Request access to data products within scope. |

> **Important**: To add data assets to a data product, Data Product Owners and Data Stewards also need Data Map permissions to read those data assets in Data Map.

Learn more about [data governance roles and permissions](https://learn.microsoft.com/purview/data-governance-roles-permissions).

## Additional Roles for Access Management

| Role | System | Purpose |
|------|--------|---------|
| **Manager** | Microsoft Entra ID | First tier of approval when manager approval is configured. Automatically identified from requestor's Entra ID profile. |
| **Privacy Reviewer** | Named in request | Second tier of approval when privacy review is configured. Requestor names the privacy reviewer during the access request. |
| **Information Protection Admin** | Microsoft Purview Risk & Compliance | Configure sensitivity labels and information protection policies that can be used with data assets in data products. **Part of Microsoft Purview Information Protection roles.** |
| **IAM Owner / Contributor** | Azure / Fabric | Manually provision access to underlying data assets (Azure SQL, ADLS Gen2, Fabric, etc.) as part of the approval process. |

Learn more about [Information Protection roles and permissions](https://learn.microsoft.com/defender-office-365/scc-permissions#roles-in-microsoft-defender-for-office-365-and-microsoft-purview).

# Getting Started

To implement data product access policies in your organization:

## 1. Create Governance Structure

1. **Create Governance Domain** - Establish governance domains that represent your data ownership structure - review prior sections to create this.
2. **Assign Governance Domain Owners** - Designate domain owners who can delegate permissions
3. **Assign Data Stewards and Data Product Owners** - Assign roles to business and technical data owners

## 2. Configure Domain-Level Policies (Optional)

1. Navigate to **Unified Catalog** > **Catalog management** > **Governance domains**
2. Select your governance domain
3. Select **Manage policies**
4. Configure domain-level policies:
   - Manager approval requirements
   - No-copy attestations
   - Custom attestations
5. These policies will automatically apply to all data products in the domain

## 3. Configure Data Product Access Policies

1. Create or edit a data product (must be in unpublished/draft state)
2. Select the **Manage policies** tab
3. Configure access policies:
   - **Permitted Access**: Add authorized usage purposes (business justifications)
   - **Approval Requirements**: Enable manager approval and/or privacy review
   - **Access Request Approvers**: Add users or groups who can approve requests (data product owners are added by default)
   - **Access Provider** (optional): Designate users who will manually provision access to data assets
   - **Attestations**: Configure no-copy policies and add custom attestations with supporting documentation
4. Select **Preview request form** to see the user experience
5. Select **Save changes**
6. Publish the data product to make it available for access requests

## 4. Manage Access Requests

### View and Approve Requests

1. Navigate to **Unified Catalog** > **Catalog management** > **Requests and approvals**
2. Select **Waiting for my response** to see pending requests
3. Select an access request to view details
4. Review the requestor's information, usage purpose, and attestations
5. **Approve** or **Deny** the request
6. If you're the last approver or an access provider:
   - Manually provision access to each data asset through the source system (Azure portal, Fabric workspace, etc.)
   - Record the provisioning status for each asset
   - Provide instructions to the data consumer on how to access the data
   - Mark the request as **Completed**

### Approve via Email

1. Select the **Approval request link** in the email notification
2. Review request details in the Unified Catalog
3. Approve or deny the request
4. If you're the last approver, provision access and mark as complete

### Monitor Request Status

Request statuses include:
- **Pending**: Awaiting approver review
- **Declined**: Denied by an approver
- **Approved**: Approved but access not yet provisioned
- **Completed**: Access provisioned and available to requestor

## 5. Revoke Access

To revoke a user's access to a data product:

> **Note**: Only data product owners can revoke access.

1. **Manually remove access** from the underlying data assets (Azure, Fabric, etc.)
2. **Delete the access request** in Unified Catalog:
   - Navigate to **Catalog management** > **Requests**
   - Select the governance domain and the request
   - Select **Delete** from the Access Request flyout

> **Important**: You must complete both steps. If you only remove access from the data source without deleting the request, the user will still show as having access in the Unified Catalog.

## Advanced Configuration

### Configure Policies on Glossary Terms and Critical Data Elements

Data stewards can configure access policies on glossary terms and critical data elements that will be inherited by data products using those terms or elements:

1. Navigate to a glossary term or critical data element
2. Select **Manage policies**
3. Configure inherited policies:
   - Manager approval requirements
   - No-copy attestations
   - Custom attestations
4. Data products associated with these business concepts will automatically inherit and aggregate these policies

### Disable Access Management for Specific Data Products

If you use an external access management solution or don't want access requests for a specific data product:

1. Edit the data product (draft state)
2. Select the **Manage policies** tab
3. Scroll to the **Workflows** section
4. Enable the **Disable Access Management** checkbox
5. Save and publish the data product

When disabled, the "Request access" button won't appear and no access policies apply to that data product.

For detailed guidance, see [Manage data product access policies](https://learn.microsoft.com/purview/unified-catalog-data-product-access-policies).

---

> **Legacy Note**: Classic data policy enforcement (data owner policies, DevOps policies, protection policies) is a separate feature focused on direct Azure resource-level access control. For information about classic data policy enforcement, see [Data Policy Enforcement](https://learn.microsoft.com/purview/how-to-enable-data-policy-enforcement).
