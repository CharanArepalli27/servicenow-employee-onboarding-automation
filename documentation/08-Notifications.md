# Notifications

Notifications are used in the Employee Onboarding Automation project to keep the required users and teams informed about important onboarding events.

The project contains three notifications.

---

## 1. Manager Approval Requested

### Purpose

Notify the selected manager when a new Employee Onboarding Request requires approval.

### Configuration

**Notification Name:**  
Manager Approval Requested

**Subject:**  
Employee Onboarding Approval Required

**Recipient:**  
Manager selected in the Catalog Item

### Notification Content

The email includes important onboarding information such as:

- Employee Name
- Employee ID
- Department
- Job Role
- Start Date
- Approval requirement

### Flow Implementation

The notification is implemented in the **On Boarding New Employee Flow**.

The notification is sent before the **Ask for Approval** action.

### Expected Behavior

When an onboarding request is submitted:

1. The request reaches the Manager Approval stage.
2. The selected manager receives an approval notification.
3. The manager can review the onboarding request.
4. The manager approves or rejects the request.

---

## 2. Onboarding Request Rejected

### Purpose

Notify the requester when the manager rejects the onboarding request.

### Configuration

**Notification Name:**  
Onboarding Request Rejected

**Subject:**  
Employee Onboarding Request Rejected

**Recipient:**  
Requested For → Email

### Flow Implementation

The notification is implemented in the rejection branch of the **On Boarding New Employee Flow**.

The sequence is:

```text
Ask for Approval
      ↓
Approval Rejected
      ↓
Send Rejection Notification
      ↓
Update Requested Item
      ↓
State = Closed Incomplete
