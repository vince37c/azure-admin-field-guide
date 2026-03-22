# Azure Administrator Playbook

A hands-on Azure Administrator lab repository documenting the creation and configuration of core Azure services aligned with AZ-104 concepts.

## Purpose
This repository captures practical exercises used to build familiarity with Azure administration tasks including resource management, networking, identity, storage, and monitoring.

Each lab includes:
- Objective
- Resources Created
- Prerequisites
- Build steps
- Validation
- Screenshots
- Cleanup instructions

## Lab Catalog

| Lab | Description |
|-----|------------|
| 01 | Resource Groups |
| 02 | Virtual Machine |
| 03 | Network Security Group |
| 04 | Azure Budget + Cost Alerts |
| 05 | Storage Account + File Share |

## Standards

### Naming
rg-<project>-<environment>-<region>

Example:
rg-adminlabs-dev-eastus

### Tagging

Tags help organize and manage Azure resources.

Standard tags used in these labs:

- **Owner** – identifies who manages the resource  
- **Environment** – identifies the deployment stage (Dev/Test/Prod)  
- **Project** – identifies the workload or project  

---

## Repo Notes
- Screenshots live inside each lab folder.
- No secrets are stored.
- Cleanup steps are included to avoid unnecessary Azure costs.
