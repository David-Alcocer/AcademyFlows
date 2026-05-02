# ⚙️ Automation Engine ("Bureaucratic Pull Request")

The core of AcademyFlows is the automation of approvals and feedback using Microsoft Power Automate and the Microsoft Teams API.

## Trigger Specifications

* **Connector:** SharePoint
* **Action:** `When a file is created or modified (properties only)`
* **Surgical Routing:** To save server resources, the flow is strictly limited to the specific working folder path (e.g., `/Shared Documents/Trámites - Facturas/Facturas`).

## State Machine (Logic Tree)

### 1. The Listener (Initial Filter)
Evaluates if the document is ready to be reviewed by a coordinator.
* **Condition:** `[Status Value]` is equal to `2. In Review`
* If `False`, the flow terminates immediately (resource optimization).

### 2. The "Pull Request"
If `True`, an Adaptive Card is deployed to the Coordinator's Microsoft Teams.
* **Action:** `Start and wait for an approval` (Approve/Reject)
* **Injected Data:** File Name, Dynamic link to the document, and Sender's Email.

### 3. The Automatic Merge (Resolution)
The system encapsulates the coordinator's response inside a `For each` loop (by platform design) and evaluates the outcome.
```json
{
  "Evaluation_Logic": {
    "Variable": "Outcome",
    "Operator": "is equal to",
    "Expected_Value": "Approve"
  }
}