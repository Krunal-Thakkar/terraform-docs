---
title: ReadMe
Description: ReadMe page
weight: 5
---

# Terraform Provider for Dell Technologies PowerFlex

The Terraform Provider for Dell Technologies (Dell) PowerFlex allows Data Center and IT administrators to use Hashicorp Terraform to automate and orchestrate the provisioning and management of Dell PowerFlex storage systems.

The Terraform Provider can be used to manage SDCs, volumes, snapshots, snapshot-policies, storage pools, SDSs and protection domains.

## Table of contents

* [License](#license)
* [Prerequisites](#prerequisites)
* [List of DataSources in Terraform Provider for Dell PowerFlex](#list-of-datasources-in-terraform-provider-for-dell-powerflex)
* [List of Resources in Terraform Provider for Dell PowerFlex](#list-of-resources-in-terraform-provider-for-dell-powerflex)
* [Releasing, Maintenance and Deprecation](#releasing-maintenance-and-deprecation)

## License
The Terraform Provide for PowerFlex is released and licensed under the MPL-2.0 license. See [LICENSE](https://github.com/dell/terraform-provider-powerflex/blob/main/LICENSE) for the full terms.

## Prerequisites

| **Terraform Provider** | **PowerFlex/VxFlex OS Version** | **OS** | **Terraform** | **Golang** | **goscaleio commit id**              |
|---------------------|-----------------------|-------|--------------------|--------------------------|--------------------|
| v1.0.0 | 3.6 | Ubuntu22.04 <br> RHEL8.x <br> RHEL7.x | 1.3.2 <br> 1.2.9 | 1.19.x | bfd3fae12e7b

## List of DataSources in Terraform Provider for Dell PowerFlex
  * SDC
  * Storage pool
  * Volume
  * SDS
  * Protection Domain
  * Snapshot Policy

## List of Resources in Terraform Provider for Dell PowerFlex
  * SDC
  * Storage pool
  * Volume
  * SDS
  * Snapshot

## Installation of Terraform Provider for Dell PowerFlex

## Installation from public repository

The provider will be fetched from the public repository and installed by terraform automatically.
Create a file called `main.tf` in your workspace with the following contents

```terraform
terraform {
  required_providers {
    powerflex = {
      version = "1.0.0"
      source  = "registry.terraform.io/dell/powerflex"
    }
  }
}
```
Then, in that workspace, run
```
terraform init
``` 

## Installation from source code

Dependencies: Go 1.19.x, make
Run
```
git clone https://github.com/dell/terraform-provider-powerflex.git
cd terraform-provider-powerflex
make install
```
Then follow [installation from public repo](#installation-from-public-repository)

## SSL Certificate Verification

For SSL verifcation on RHEL, below steps can be performed:
 * Copy the CA certificate to the `/etc/pki/ca-trust/source/anchors` path of the host by any external means.
 * Import the SSL certificate to host by running
```
update-ca-trust extract
```



## Releasing, Maintenance and Deprecation

Terraform Provider for Dell Technnologies PowerFlex follows [Semantic Versioning](https://semver.org/).

New version will be release regularly if significant changes (bug fix or new feature) are made in the provider.

Released code versions are located on tags with names of the form "vx.y.z" where x.y.z corresponds to the version number.
