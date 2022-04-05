---
title: 'Running Python Scripts in Terraform '
description: 'One day you will need to create infrastructure in Terraform using Python.
  That day was yesterday for me. '
permalink: posts/{{ title | slug }}/index.html
date: 2022-04-04T04:00:00Z
tags:
- Schema Registry
- Azure
- Terraform
- Python

---
More often than not, Terraform takes care of everything. Almost every resource I need is available in Terraform, and I'm usually just one init --upgrade away from creating new resources in Azure and Databricks. But some resources are so new that there is no current support in Terraform. 

Azure Schema Registry is a good example of a resource that doesn't have any CLI commands I can run, but does have support in the Azure Python SDK. Since I never turn down an opportunity to write some Python, we can write a Python script to execute every time changes are made to our schemas. 

## Directory Structure

```css
root
--terraform
--scripts
--schemas
```

## Writing Our Script