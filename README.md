# 🐺 AcademyFlows: Active Document Management System

AcademyFlows is a Microsoft 365-based software architecture designed to transform static file repositories at the Universidad Autónoma de Yucatán (UADY) into automated State Machines. 

It eliminates the use of nested subfolders through a metadata-driven **Flat Architecture** and automates bureaucratic approvals, drawing heavy inspiration from the GitHub *Pull Request* model.

## 🏗️ System Architecture

The system is built upon three main layers:
1. **Database (Backend):** A SharePoint Document Library enforcing strict Choice-type schemas.
2. **User Interface (Frontend):** Indexed SharePoint Views (Expanded Grouped Lists) that simulate a Kanban Board experience.
3. **Logic Engine (Middleware):** Microsoft Power Automate and Microsoft Teams Approvals API.

### The "Zero Subfolders" Paradigm
Traditional folder structures hide information and complicate audits. AcademyFlows utilizes indexed metadata, allowing for:
* Millisecond queries via Enterprise Search.
* Automatic UI clean-up (completed workflows are hidden from the daily operational view).
* Generation of Historical Views for compliance and auditing.

## 🚀 Scalability and Implementation at UADY

AcademyFlows is designed to be highly scalable across any university department (e.g., FMAT Linkage, Administrative Secretariat, Student Control).

| Feature | Operational Benefit at UADY |
| :--- | :--- |
| **Standardization** | Eliminates spelling errors and typos in workflow tracking. |
| **Compliance & Auditing** | The Teams Approvals Center maintains an immutable log of who authorized each document and when. |
| **User Adoption** | A color-coded, Drag & Drop interface that requires zero technical training for staff. |
| **Omnichannel Access** | Coordinators can approve or reject requests from their mobile phones, Microsoft Teams, or institutional Outlook. |

## 📊 Process Flow (Diagram)
```mermaid
graph TD
    A[Student Uploads Document] -->|State: 1. Received| B(Initial Review)
    B -->|Staff drags file to| C{State: 2. In Review}
    C -->|Automatic Webhook| D[Pull Request to Teams]
    D -->|Coordinator Approves| E((State: 4. Completed))
    D -->|Coordinator Rejects with Comments| F((State: 3. Fix))
    F -->|Notification Trigger| G[Feedback Email sent to Student]
    G --> A