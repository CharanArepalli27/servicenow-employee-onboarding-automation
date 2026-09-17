# Main Flow - Employee Onboarding Automation

## Flow Name

On Boarding New Employee Flow

## Purpose

The main Flow Designer flow automates the employee onboarding process after a New Employee Onboarding Request is submitted.

The flow handles:

- Catalog request data collection
- Manager approval
- Approval rejection
- Conditional provisioning
- Automatic SCTASK creation
- Assignment group routing through a reusable Subflow

---

# Flow Overview

```text
Service Catalog Request
        ↓
Get Catalog Variables
        ↓
Manager Approval Notification
        ↓
Ask for Approval
        ↓
     Approval?
     /       \
  Rejected   Approved
     ↓          ↓
Close RITM     Check Requirements
Incomplete        ↓
             Create SCTASKs
