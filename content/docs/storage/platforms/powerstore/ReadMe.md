---
title: ReadMe
Description: ReadMe page
weight: 5
---

# Terraform Provider for Dell Technologies PowerStore

The Terraform Provider for Dell Technologies (Dell) PowerStore allows Data Center and IT administrators to use Hashicorp Terraform to automate and orchestrate the provisioning and management of Dell PowerStore storage systems.

The Terraform Provider can be used to manage volumes, snapshot rules, protection policies and storage containers.

## Table of contents

* [License](#license)
* [Prerequisites](#prerequisites)
* [List of Resources in Terraform Provider for Dell PowerStore](#list-of-resources-in-terraform-provider-for-dell-powerstore)
* [List of DataSources in Terraform Provider for Dell PowerStore](#list-of-datasources-in-terraform-provider-for-dell-powerstore)
* [Releasing, Maintenance and Deprecation](#releasing-maintenance-and-deprecation)

## License
The Terraform Provide for PowerStore is released and licensed under the MPL-2.0 license. See [LICENSE](https://github.com/dell/terraform-provider-powerstore/blob/main/LICENSE) for the full terms.

## Prerequisites

| **Terraform Provider** | **PowerStore Version** | **OS** | **Terraform** | **Golang** | **Terraform Plugin Framework version**              |
|---------------------|-----------------------|-------|--------------------|--------------------------|--------------------|
| v1.0.0 | 3.0 | Ubuntu 22.04 <br> RHEL 8.x <br> RHEL 7.x | 1.3.2 <br> 1.2.9 <br> 1.3.2 <br> 1.2.9 <br> | 1.19.x | 1.0.1

## List of Resources in Terraform Provider for Dell PowerStore
  * Volume
  * Snapshot Rule
  * Protection Policy
  * Storage Container

## List of DataSources in Terraform Provider for Dell PowerStore
  * Volume

## Installation of Terraform Provider for Dell PowerFStore

## Installation from public repository

The provider will be fetched from the public repository and installed by terraform automatically.
Create a file called `main.tf` in your workspace with the following contents

```terraform
terraform {
  required_providers {
    powerstore = {
      version = "0.0.1"
      source = "registry.terraform.io/dell/powerstore"
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
git clone https://github.com/dell/terraform-provider-powerstore.git
cd terraform-provider-powerstore
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

Terraform Provider for Dell Technnologies PowerStore follows [Semantic Versioning](https://semver.org/).

New version will be released regularly if significant changes (bug fix or new feature) are made in the provider.

Released code versions are located on tags with names of the form "vx.y.z" where x.y.z corresponds to the version number.