# Testing

The Employee Onboarding Automation project was tested end-to-end to verify that the Catalog Item, client-side validations, UI Policies, approval process, Flow Designer automation, SCTASK creation, notifications, and reporting work as expected.

---

## 1. Catalog Item Testing

The **New Employee Onboarding Request** Catalog Item was tested with different combinations of employee, job, equipment, application, and workplace requirements.

### Scenarios Tested

- Employee information can be entered successfully.
- Department and Job Role fields work correctly.
- Job Role choices change dynamically based on Department.
- Manager can be selected from the User reference field.
- Equipment requirements can be selected.
- Application access requirements can be selected.
- Additional information can be provided.

### Result

Catalog Item fields accepted valid inputs and displayed the expected dynamic behavior.

---

## 2. UI Policy Testing

The conditional UI Policies were tested by changing the related fields.

### Contractor End Date

```text
Employment Type = Contractor
→ Contractor End Date is displayed and mandatory
