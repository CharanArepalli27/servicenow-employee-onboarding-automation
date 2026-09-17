# SCTASK Completion Flow

## Flow Name

Employee Onboarding Task Completion Flow

## Purpose

This is a separate Flow Designer flow that monitors employee onboarding SCTASKs and determines when the parent RITM can be closed.

The Flow checks the state of all Catalog Tasks associated with the same Requested Item.

It handles two possible outcomes:

- All onboarding SCTASKs are completed successfully → RITM is Closed Complete
- Any onboarding SCTASK is Closed Incomplete → RITM is Closed Incomplete

---

# Flow Trigger

### Trigger Type

Record Updated

### Table

Catalog Task [sc_task]

### Condition

The SCTASK state changes to one of the following final states:

- Closed Complete
- Closed Incomplete

### Run Trigger

Once

---

# Flow Overview

```text
SCTASK State Changes
        ↓
Check for Closed Incomplete Tasks
        ↓
Any Closed Incomplete Task?
       / \
     YES  NO
      ↓    ↓
Close RITM   Check for Pending Tasks
Incomplete         ↓
              Any Pending Tasks?
                 /       \
               YES        NO
                ↓          ↓
             Do Nothing   Close RITM
                          Complete
