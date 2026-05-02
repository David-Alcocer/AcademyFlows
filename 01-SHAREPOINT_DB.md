# 🗄️ Database Schema and Kanban View

The AcademyFlows database resides within a SharePoint Document Library. Data integrity is maintained by completely avoiding free-text columns and enforcing chronological flows through a numbered prefix system.

## Data Dictionary (Metadata)

| Column Name | Data Type | Required | Description / Usage |
| :--- | :--- | :--- | :--- |
| `Name` | System (Text) | Yes | Original file name (e.g., PDF). |
| `Sender` | Person or Group | Yes | Institutional email of the student/user. |
| `Status` | Choice | Yes | The core engine of the State Machine. |

### Strict Configuration of the `Status` Column
To force the chronological order of the funnel and apply color psychology, the exact values must be set as follows (including the numbers):

1. `1. Received` *(Grey/Blue Pill)* - Default Value.
2. `2. In Review` *(Yellow Pill)* - Triggers the approval workflow.
3. `3. Fix` *(Red Pill)* - Requires action from the end-user.
4. `4. Completed` *(Green Pill)* - End of the process.

## 🖥️ Frontend Configuration (The Kanban)

Due to User Interface restrictions in institutional tenants regarding Document Libraries, the vertical Kanban Board is emulated using an **Expanded Grouped List**.

**Deployment Steps:**
1. Create a new view of type **List** (e.g., "Workflow Management").
2. In the classic view settings, scroll down to the **Group By** section.
3. Select the `Status` column in **Ascending** order.
4. Set the default grouping to **Expanded**.

This setup unlocks the functional *Drag and Drop* feature, which automatically updates the metadata in the underlying SQL database without requiring users to open property panels.