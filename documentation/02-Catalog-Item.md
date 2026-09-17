# 📋 Catalog Item Configuration

## Catalog

**Category:** Employee Services

**Catalog Item:** New Employee Onboarding Request

### Short Description

Submit a request to onboard a new employee and automatically provision the required equipment, applications, and workplace services.

---

# 🧩 Variable Sets

The Catalog Item uses five Variable Sets.

---

## 1️⃣ VS – Employee Information

| Variable | Type | Mandatory |
|---|---|---|
| Employee Name | Single Line Text | Yes |
| Employee ID | Single Line Text | Yes |
| Employee Email | Email | Yes |
| Employee Phone | Single Line Text | Yes |
| Start Date | Date | Yes |
| Employment Type | Select Box | Yes |
| Contractor End Date | Date | No |

### Employment Type Choices

| Label | Value |
|---|---|
| Full Time | `full_time` |
| Contractor | `contractor` |
| Intern | `intern` |
| Temporary | `temporary` |

`Contractor End Date` is displayed and made mandatory only when Employment Type is Contractor.

---

# 2️⃣ VS – Job Information

| Variable | Type | Mandatory |
|---|---|---|
| Department | Select Box | Yes |
| Job Role | Select Box | Yes |
| Manager | Reference → User [sys_user] | Yes |
| Work Location | Select Box | Yes |

### Department Choices

| Label | Value |
|---|---|
| IT | `it` |
| HR | `hr` |
| Finance | `finance` |
| Sales | `sales` |
| Marketing | `marketing` |
| Operations | `operations` |

### Job Role

The Job Role field is dynamically populated based on the selected Department using a Catalog Client Script.

### IT Roles

- ServiceNow Developer
- Network Engineer
- System Administrator
- Help Desk Analyst
- IT Manager

### HR Roles

- HR Executive
- Recruiter
- HR Manager
- HR Analyst

### Finance Roles

- Accountant
- Financial Analyst
- Finance Manager
- Accounts Payable Specialist

### Sales Roles

- Sales Executive
- Account Manager
- Sales Manager
- Business Development Executive

### Marketing Roles

- Digital Marketing Specialist
- Content Marketing Specialist
- Marketing Manager
- SEO Specialist

### Operations Roles

- Operations Executive
- Operations Analyst
- Operations Manager
- Project Coordinator

### Work Location Choices

- Bengaluru
- Hyderabad
- Chennai
- Mumbai
- Remote

---

# 3️⃣ VS – Equipment Requirements

| Variable | Type | Mandatory |
|---|---|---|
| Laptop Required | Yes/No | Yes |
| Laptop Type | Select Box | Conditional |
| Monitor Required | Yes/No | Yes |
| Monitor Quantity | Integer | Conditional |
| Mobile Required | Yes/No | Yes |
| Headset Required | Yes/No | Yes |

### Laptop Type Choices

- Windows Laptop
- MacBook
- Linux Laptop

`Laptop Type` is displayed and made mandatory when `Laptop Required = Yes`.

`Monitor Quantity` is displayed and made mandatory when `Monitor Required = Yes`.

---

# 4️⃣ VS – Application Access

| Variable | Type | Mandatory |
|---|---|---|
| Email Access | Yes/No | Yes |
| Teams Access | Yes/No | Yes |
| ServiceNow Access | Yes/No | Yes |
| Salesforce Access | Yes/No | Yes |
| Salesforce Role | Select Box | Conditional |
| VPN Access | Yes/No | Yes |

### Salesforce Role Choices

- Sales User
- Sales Manager
- Read Only User

`Salesforce Role` is displayed and made mandatory when `Salesforce Access = Yes`.

---

# 5️⃣ VS – Additional Information

| Variable | Type | Mandatory |
|---|---|---|
| Special Requirements | Multi Line Text | No |
| Additional Comments | Multi Line Text | No |

---

# 🔄 Catalog Item Behavior

The form dynamically responds to user selections.

### Example

```text
Employment Type = Contractor
          ↓
Contractor End Date appears
          ↓
Contractor End Date becomes mandatory
