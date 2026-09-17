# UI Policies

UI Policies are used in the New Employee Onboarding Request Catalog Item to control field visibility, mandatory behavior, and field values based on user selections.

## 1. Contractor End Date

### Purpose

Display and make the Contractor End Date field mandatory when Employment Type is Contractor.

### Condition

Employment Type is Contractor

### UI Policy Action

| Field | Visible | Mandatory |
|---|---|---|
| Contractor End Date | True | True |

### Reverse / Else Behavior

When the condition is false:

- Hide Contractor End Date
- Remove the mandatory requirement
- Clear the field value

### Expected Behavior

Employment Type = Contractor  
→ Contractor End Date is displayed  
→ Contractor End Date becomes mandatory

---

## 2. Laptop Type

### Purpose

Display and make the Laptop Type field mandatory when a laptop is required.

### Condition

Laptop Required is Yes

### UI Policy Action

| Field | Visible | Mandatory |
|---|---|---|
| Laptop Type | True | True |

### Reverse / Else Behavior

When the condition is false:

- Hide Laptop Type
- Remove the mandatory requirement
- Clear the field value

### Expected Behavior

Laptop Required = Yes  
→ Laptop Type is displayed  
→ Laptop Type becomes mandatory

---

## 3. Monitor Quantity

### Purpose

Display and make the Monitor Quantity field mandatory when a monitor is required.

### Condition

Monitor Required is Yes

### UI Policy Action

| Field | Visible | Mandatory |
|---|---|---|
| Monitor Quantity | True | True |

### Reverse / Else Behavior

When the condition is false:

- Hide Monitor Quantity
- Remove the mandatory requirement
- Clear the field value

### Expected Behavior

Monitor Required = Yes  
→ Monitor Quantity is displayed  
→ Monitor Quantity becomes mandatory

---

## 4. Salesforce Role

### Purpose

Display and make the Salesforce Role field mandatory when Salesforce Access is required.

### Condition

Salesforce Access is Yes

### UI Policy Action

| Field | Visible | Mandatory |
|---|---|---|
| Salesforce Role | True | True |

### Reverse / Else Behavior

When the condition is false:

- Hide Salesforce Role
- Remove the mandatory requirement
- Clear the field value

### Expected Behavior

Salesforce Access = Yes  
→ Salesforce Role is displayed  
→ Salesforce Role becomes mandatory

---

## UI Policy Summary

| UI Policy | Condition | Controlled Field |
|---|---|---|
| Contractor End Date | Employment Type = Contractor | Contractor End Date |
| Laptop Type | Laptop Required = Yes | Laptop Type |
| Monitor Quantity | Monitor Required = Yes | Monitor Quantity |
| Salesforce Role | Salesforce Access = Yes | Salesforce Role |

---

## Testing

Each UI Policy was tested through the Catalog Item form.

The following scenarios were verified:

- Conditional field visibility
- Conditional mandatory behavior
- Field value clearing when the condition becomes false
- Correct behavior when selections are changed

---

## Result

UI Policies ensure that users only see and provide information relevant to their onboarding requirements, reducing unnecessary fields and preventing incomplete submissions.
