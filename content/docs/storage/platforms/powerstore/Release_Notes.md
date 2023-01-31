---
title: Release Notes
Description: Release Notes page
weight: 5
---

**Terraform Provider for Dell Technologies PowerStore**
=========================================
### Release Notes 1.0.0

>   © 2023 Dell Inc. or its subsidiaries. All rights reserved. Dell,
>   and other trademarks are trademarks of Dell Inc. or its
>   subsidiaries. Other trademarks may be trademarks of their respective
>   owners.

Content
-------
These release notes contain supplemental information about Terraform Provider for Dell Technologies(Dell) PowerStore.

-   [Revision History](#revision-history)
-   [Product Description](#product-description)
-   [New Features & Enhancements](#new-features--enhancements)
-   [Known Issues](#known-issues)
-   [Limitations](#limitations)
-   [Distribution](#distribution)
-   [Documentation](#documentation)

Revision history
----------------
The table in this section lists the revision history of this document.

Table 1. Revision history

| Revision | Date      | Description                                               |
|----------|-----------|-----------------------------------------------------------|
| 01       | January 2023  | Current release of Terraform Provider for Dell Technologies PowerStore 1.0.0 |

Product Description
-------------------
The Terraform Provider for Dell Technologies (Dell) PowerStore allows Data Center and IT administrators to use Hashicorp Terraform to automate and orchestrate the provisioning and management of Dell PowerStore storage systems.

The Terraform Provider can be used to manage volumes, snapshot rules, protection policies and storage containers.

New features & enhancements
---------------------------
List of Resources and supported operations in Terraform Provider for Dell PowerStore
  * Volume - Create, Read, Update, Delete, Import
  * Snapshot Rule - Create, Read, Update, Delete, Import
  * Protection Policy - Create, Read, Update, Delete, Import
  * Storage Container - Create, Read, Update, Delete, Import

List of DataSources and supported operations in Terraform Provider for Dell PowerStore
  * Volume - Read

Known issues
------------
- Creating/Modifying protection policy with replication or snapshot rule throws inconsistent result after apply error.
- Modification for few attributes of volume resource is giving state and plan mismatch error.

Limitations
-----------
There are no known limitations.

Distribution
----------------
The software package is available for download from the [Terraform Provider for PowerStore GitHub](https://github.com/dell/terraform-provider-powerstore/tree/1.0.0) page.

Documentation
-------------
The documentation is available on [Terraform Provider for PowerStore GitHub](https://github.com/dell/terraform-provider-powerstore/tree/1.0.0/docs)
page. It includes these:
- README
- Release Notes (this document)
- Product Guide
