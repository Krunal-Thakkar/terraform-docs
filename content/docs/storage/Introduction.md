---
title: Introduction
Description: Introduction page
weight: 1
---

In the fast-moving, competitive and technology-driven business environment, companies are adopting DevOps practices to accelerate application delivery and rapidly deliver new capabilities to respond to pressing business needs. This growing emphasis on DevOps is placing an extra burden on storage infrastructure teams as they are expected to offer:

<ul>
<li>Automated, reliable and consistent business processes</li>
<li>Dynamic, automated, code driven storage infrastructure to manage, control and administer storage rapidly</li>
<li>Transparent workflows with the flexibility to use tools/orchestrators of choice</li>
<li>Lower TCO</li>
</ul>

Dell Technologies DevOps initiative is targeted at enabling our customers so that they can provide access to fast, automated and agile storage infrastructure to their App Developers and the IT Operations teams.  

Terraform is a popular Infrastructure as Code (IaC) tool that enables IT Ops/Dev Ops personnel securely and efficiently build, configure and deploy infrastructure configuration using human-readable configuration files or plans written in Hashicorp Configuration Language (HCL). These plans can then be versioned, reused and shared thus enabling a consistent workflow to provision and manage infrastructure. Terraform Providers are plugins that implement resource types across different cloud platforms and vendors.

Within the DevOps initiative, this program includes development of Terraform providers for Storage arrays. Terraform providers for Storage Arrays will enable the operations to rapidly provision storage infrastructure with accuracy to respond to the fast-paced needs of DevOps engineers. We will be developing the Terraform providers in phases. In Phase I, we will be developing the following terraforms providers :

<ul>
<li><b>Terraform Provider for PowerStore:</b> A custom "PowerStore" Terraform provider will provide resources and data sources that can be consumed to write a Terraform plan to provision and deploy PowerStore arrays. This enables DevOps users to manage their PowerStore infrastructure in a repeatable, predictable, scalable manner.</li>
<li><b>Terraform Provider for PowerFlex:</b> A custom "PowerFlex" Terraform provider will provide resources and data sources that can be consumed to write a Terraform plan using a declarative syntax to provision and deploy PowerFlex. This enables DevOps users to manage their PowerFlex infrastructure in a repeatable, predictable, scalable manner.</li>
</ul>