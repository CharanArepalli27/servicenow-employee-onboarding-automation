# Catalog Client Scripts

Catalog Client Scripts are used in the New Employee Onboarding Request Catalog Item to provide dynamic behavior and client-side validation.

The project uses Catalog Client Scripts for:

1. Dynamic Job Role population
2. Start Date validation
3. Employee Email validation
4. Monitor Quantity validation
5. Employee Phone validation
6. Employee ID validation
7. Final submission validation

---

## 1. Dynamic Job Role Based on Department

### Type

onChange

### Variable

`department`

### Purpose

Dynamically populate the Job Role choices based on the selected Department.

### Script

```javascript
function onChange(control, oldValue, newValue, isLoading) {

    if (isLoading) {
        return;
    }

    g_form.clearOptions('job_role');

    g_form.addOption('job_role', 'none', '-- Select Job Role --');

    if (newValue == 'it') {

        g_form.addOption('job_role', 'servicenow_developer', 'ServiceNow Developer');
        g_form.addOption('job_role', 'network_engineer', 'Network Engineer');
        g_form.addOption('job_role', 'system_administrator', 'System Administrator');
        g_form.addOption('job_role', 'help_desk_analyst', 'Help Desk Analyst');
        g_form.addOption('job_role', 'it_manager', 'IT Manager');

    } else if (newValue == 'hr') {

        g_form.addOption('job_role', 'hr_executive', 'HR Executive');
        g_form.addOption('job_role', 'recruiter', 'Recruiter');
        g_form.addOption('job_role', 'hr_manager', 'HR Manager');
        g_form.addOption('job_role', 'hr_analyst', 'HR Analyst');

    } else if (newValue == 'finance') {

        g_form.addOption('job_role', 'accountant', 'Accountant');
        g_form.addOption('job_role', 'financial_analyst', 'Financial Analyst');
        g_form.addOption('job_role', 'finance_manager', 'Finance Manager');
        g_form.addOption('job_role', 'accounts_payable_specialist', 'Accounts Payable Specialist');

    } else if (newValue == 'sales') {

        g_form.addOption('job_role', 'sales_executive', 'Sales Executive');
        g_form.addOption('job_role', 'account_manager', 'Account Manager');
        g_form.addOption('job_role', 'sales_manager', 'Sales Manager');
        g_form.addOption('job_role', 'business_development_executive', 'Business Development Executive');

    } else if (newValue == 'marketing') {

        g_form.addOption('job_role', 'digital_marketing_specialist', 'Digital Marketing Specialist');
        g_form.addOption('job_role', 'content_marketing_specialist', 'Content Marketing Specialist');
        g_form.addOption('job_role', 'marketing_manager', 'Marketing Manager');
        g_form.addOption('job_role', 'seo_specialist', 'SEO Specialist');

    } else if (newValue == 'operations') {

        g_form.addOption('job_role', 'operations_executive', 'Operations Executive');
        g_form.addOption('job_role', 'operations_analyst', 'Operations Analyst');
        g_form.addOption('job_role', 'operations_manager', 'Operations Manager');
        g_form.addOption('job_role', 'project_coordinator', 'Project Coordinator');
    }
}
