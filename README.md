# servicenow-employee-onboarding-automation
End-to-end ServiceNow Employee Onboarding automation using Service Catalog, Flow Designer, UI Policies, Catalog Client Scripts, Subflows, Notifications, Reports and Platform Analytics.
# 🚀 Smart Employee Onboarding & IT Provisioning Automation — ServiceNow

An end-to-end **ServiceNow Employee Onboarding automation project** built using Service Catalog, Flow Designer, Catalog Client Scripts, UI Policies, Subflows, Notifications, Reports and Platform Analytics.

The project automates the onboarding journey from **request submission → manager approval → provisioning task creation → task completion → RITM closure → reporting**.

---

## 🎯 Project Objective

The objective of this project is to automate a typical employee onboarding process where multiple teams may need to provide:

* 💻 Laptop
* 🖥️ Monitor
* 📱 Mobile
* 🎧 Headset
* 🔐 Application access
* 🏢 Workplace services

Instead of manually coordinating these activities, the ServiceNow workflow automatically creates and tracks the required provisioning tasks.

---

## 🔄 End-to-End Workflow

```text
Employee / Manager
        │
        ▼
Service Catalog Request
        │
        ▼
Dynamic Catalog Form
        │
        ▼
Client-side Validations
        │
        ▼
Manager Approval
        │
        ├──────── Rejected ────────► RITM → Closed Incomplete
        │
        ▼
Conditional Provisioning
        │
        ▼
Reusable Provisioning Subflow
        │
        ├── Laptop SCTASK
        ├── Monitor SCTASK
        ├── Mobile SCTASK
        ├── Headset SCTASK
        ├── Application Access SCTASK
        └── Workplace SCTASK
        │
        ▼
SCTASK Completion Monitoring
        │
        ▼
All Tasks Completed?
        │
        ▼
RITM → Closed Complete
        │
        ▼
Reports & Platform Analytics Dashboard
```

---

## 🧩 ServiceNow Features Used

### Service Catalog

* Custom Catalog Item
* Multiple Variable Sets
* Select Box variables
* Reference variables
* Conditional variables
* Mandatory variables

### Catalog Client Scripts

* Dynamic Job Role population
* Start Date validation
* Employee Email validation
* Employee Phone validation
* Employee ID validation
* Monitor Quantity validation
* Final submission validation

### UI Policies

* Contractor End Date
* Laptop Type
* Monitor Quantity
* Salesforce Role

### Flow Designer

* Catalog trigger
* Get Catalog Variables
* Manager approval
* Conditional logic
* Create Catalog Task
* Update Requested Item
* Send Email

### Subflow

A reusable provisioning Subflow was created to avoid duplicating task-creation logic.

**Subflow:** `Create Employee Provisioning Task`

Inputs:

* Requested Item
* Task Short Description
* Task Description
* Assignment Group

Outputs:

* Task Number
* Task Sys ID

### Task Completion Automation

A separate Flow monitors `Catalog Task [sc_task]` records.

The Flow checks:

1. Whether any task was closed incomplete.
2. Whether any tasks are still pending.
3. Whether all onboarding tasks have been completed.

Based on these conditions, the parent RITM is automatically updated.

---

## 📧 Notifications

The project includes:

* Manager Approval Requested
* Employee Onboarding Request Rejected
* SCTASK Created

SCTASK completion email notifications were intentionally excluded from the final implementation.

---

## 📊 Reports

Three reports were created:

### 1. Onboarding Requests by State

Displays onboarding RITMs grouped by their current state.

### 2. Pending Onboarding Tasks by Assignment Group

Displays outstanding onboarding SCTASKs grouped by Assignment Group.

### 3. Completed Onboarding Requests

Displays the number of successfully completed onboarding requests.

---

## 📈 Platform Analytics Dashboard

### Employee Onboarding Operations Dashboard

The dashboard contains:

* Onboarding Requests by State
* Pending Onboarding Tasks by Assignment Group
* Completed Onboarding Requests

This provides an operational view of the onboarding process.

---

## 🗂️ Project Structure

```text
documentation/
├── 01-Project-Overview.md
├── 02-Catalog-Item.md
├── 03-UI-Policies.md
├── 04-Catalog-Client-Scripts.md
├── 05-Main-Flow.md
├── 06-Provisioning-Subflow.md
├── 07-Task-Completion-Flow.md
├── 08-Notifications.md
├── 09-Reports-and-Dashboard.md
└── 10-Testing.md
```

---

## 🧪 Testing

The complete workflow was tested end-to-end:

* Catalog request submission
* Dynamic field behavior
* Client-side validation
* Manager approval
* Approval rejection
* Conditional SCTASK creation
* Multiple provisioning tasks
* SCTASK state changes
* RITM completion handling
* Notifications
* Reports
* Platform Analytics dashboard

---

## 🚀 How to Recreate This Project

You can recreate this project in your own ServiceNow PDI by following the documentation in the `documentation/` folder.

> ⚠️ This repository is intended for learning and hands-on practice. Configuration names, fields and UI options may vary depending on the ServiceNow release and instance configuration.

---

## 📚 Learning Outcomes

This project helped me gain practical experience with:

* Service Catalog
* Catalog Client Scripts
* UI Policies
* Flow Designer
* Subflows
* Approvals
* Catalog Tasks
* Requested Items
* Notifications
* Reports
* Platform Analytics
* End-to-end ServiceNow automation

---

## 👨‍💻 Author

**Charan Arepalli**

ServiceNow | ITSM | Flow Designer | Service Catalog | Automation

---

⭐ If this project helps you learn ServiceNow, feel free to star the repository and explore the documentation.
