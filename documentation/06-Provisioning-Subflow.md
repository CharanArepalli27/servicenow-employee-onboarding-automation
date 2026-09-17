# Reusable Provisioning Subflow

## Subflow Name

Create Employee Provisioning Task

## Purpose

The `Create Employee Provisioning Task` Subflow is a reusable component used by the main Employee Onboarding Flow to create provisioning SCTASKs.

Instead of configuring the Create Catalog Task logic separately for every onboarding requirement, the same Subflow is called with different inputs.

This provides a reusable and maintainable task creation mechanism.

---

# Subflow Overview

```text
Main Flow
    ↓
Create Employee Provisioning Task
    ↓
Create Catalog Task Record
    ↓
Return Task Number and Task Sys ID
