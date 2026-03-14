# 🎓 AcademyFlows — Project Foundations

**Automation workflows for academic administrative processes using Microsoft 365**

This document defines the **core tools**, **key concepts**, and a **pilot workflow architecture** for designing scalable administrative automations in academic environments.

---

# 📦 Microsoft 365 Core Tools

These are the main platforms used to build the automation system.

| Tool | Purpose | Role in Automation |
|-----|-----|-----|
| Microsoft Power Automate | Workflow automation platform | Executes automated processes |
| Microsoft Outlook | Email and calendar service | Main trigger source |
| Microsoft OneDrive | Personal cloud storage | File storage for documents |
| Microsoft SharePoint | Organizational document management | Structured document repository |
| Microsoft Teams | Collaboration platform | Notifications and communication |

---

# ⚙️ Microsoft Power Automate

**Microsoft Power Automate** is a workflow automation platform that allows users to create automated processes between applications and services.

It works using **triggers** and **actions** to automate repetitive tasks.

## Core Model
Trigger → Actions → Result

## Example Workflow
Email received
↓
Detect attachment
↓
Save file to cloud storage
↓
Notify team

### Typical Capabilities

- Email processing  
- Document routing  
- Task creation  
- Notifications  
- Data synchronization  

---

# 📧 Microsoft Outlook

**Microsoft Outlook** is Microsoft's email and scheduling platform.

In workflow automation it often acts as a **trigger source**, meaning workflows can start when an email arrives.

## Example Trigger
New email received

## Example Use Cases

| Event | Automation |
|-----|-----|
| Email arrives | Save attachment |
| Email contains keyword | Categorize message |
| Email contains invoice | Store document automatically |

---

# ☁️ Microsoft OneDrive

**Microsoft OneDrive** is Microsoft's cloud file storage service.

## Main Capabilities

- File storage
- File sharing
- Version history
- Synchronization

## Role in the System
Email attachment
↓
Stored in OneDrive
↓
Organized by folder structure

---

# 🗂 Microsoft SharePoint

**Microsoft SharePoint** is a collaboration and document management platform used by organizations.

## Key Advantages

| Feature | Benefit |
|-----|-----|
| Document libraries | Organized file storage |
| Version control | Track document changes |
| Permissions | Control document access |
| Approval workflows | Manage document lifecycle |

## Typical Workflow
Document uploaded
↓
Review requested
↓
Approval process
↓
Archived in repository

---

# 💬 Microsoft Teams

**Microsoft Teams** is a collaboration and communication platform.

## Role in Automation

Teams is often used to send **notifications when workflows trigger important events**.

## Example
Document uploaded
↓
Power Automate detects change
↓
Notification sent to Teams channel

---

# 🧠 Key Automation Concepts

Understanding these concepts is essential before designing workflows.

---

# 1️⃣ Workflow

A **workflow** is a sequence of automated steps that complete a task.

## Example
Receive email
↓
Extract attachment
↓
Save document
↓
Notify staff

---

# 2️⃣ Business Process

A **business process** is a structured set of activities used by an organization to accomplish a goal.

## Example

| Step | Action |
|----|----|
| 1 | Receive invoice |
| 2 | Verify information |
| 3 | Approve document |
| 4 | Archive record |

---

# 3️⃣ Business Process Automation (BPA)

**BPA** is the use of technology to automate repetitive organizational tasks.

## Benefits

- Reduce manual work
- Increase efficiency
- Reduce human error
- Improve visibility of processes

---

# 4️⃣ Trigger

A **trigger** is the event that starts a workflow.

## Common Triggers

| Event | Example |
|-----|-----|
| Email received | Outlook |
| File uploaded | OneDrive |
| Form submitted | Microsoft Forms |

Example:
Trigger: Email with attachment received

---

# 5️⃣ Action

An **action** is a task performed after a trigger occurs.

## Examples

| Action | Description |
|-----|-----|
| Save file | Store document |
| Create task | Assign work |
| Send notification | Alert staff |

Example:
Action: Save PDF file

---

# 6️⃣ Connector

A **connector** allows different services to communicate.

## Example Integrations
Outlook → OneDrive
Outlook → SharePoint
SharePoint → Teams

Connectors allow Power Automate to move data between systems.

---

# 7️⃣ Document Management System (DMS)

A **DMS** is a system used to organize, store, and manage digital documents.

## Typical Features

| Feature | Description |
|-----|-----|
| Storage | Store files |
| Metadata | Describe documents |
| Search | Find documents easily |
| Versioning | Track document history |

SharePoint often acts as the DMS.

---

# 8️⃣ Version Control

Version control tracks changes made to a document over time.

## Example
contract_v1.pdf
contract_v2.pdf
contract_signed.pdf

This ensures document history is preserved.

---

# 9️⃣ File Naming Convention

A **file naming convention** standardizes how files are named.

## Example Pattern
CLIENT_DOCUMENTTYPE_YEAR_MONTH.pdf

## Example
ACME_INVOICE_2026_03.pdf

Benefits:

- Easier automation
- Easier search
- Better organization

---

# 🔟 Approval Workflow

An **approval workflow** ensures documents are reviewed before final use.

## Example
Create document
↓
Review requested
↓
Approval
↓
Archive

---

# 🏗 Pilot Workflow Architecture

This is a **simplified architecture for the automation system**.
          ┌─────────────┐
          │   Outlook   │
          │   (Email)   │
          └──────┬──────┘
                 │
                 ▼
       ┌──────────────────┐
       │ Power Automate   │
       │ Workflow Engine  │
       └──────┬──────┬────┘
              │      │
              ▼      ▼
    ┌────────────┐  ┌────────────┐
    │  OneDrive  │  │ SharePoint │
    │ File Store │  │ Doc System │
    └──────┬─────┘  └──────┬─────┘
           │               │
           ▼               ▼
       ┌─────────────────────────┐
       │        Teams            │
       │     Notifications       │
       └─────────────────────────┘

---

# 📁 Pilot Folder Structure

Example organization for documents.
Documents
Clients
│
├── Client_A
│ ├── Contracts
│ ├── Invoices
│ └── Reports
│
├── Client_B
│ ├── Contracts
│ ├── Invoices
│ └── Reports
│
Internal
│
├── Diplomas
├── Audits
└── Administrative


---

# 🔄 Example Automated Scenario

## Email Received
Subject: Invoice ACME March
Attachment: invoice.pdf

## Automated Flow
Email received
↓
Power Automate trigger activates
↓
Attachment detected
↓
Create client folder if not exists
↓
Save document in Invoices folder
↓
Rename document automatically
↓
Send notification to Teams

---

# 🚀 Future Improvements

Possible future automation features.

| Feature | Purpose |
|-----|-----|
| Document approval workflows | Structured reviews |
| Version history tracking | Track edits |
| Task assignments | Manage responsibilities |
| Client document classification | Organize records |
| Workflow dashboards | Monitor processes |

---

# 🎯 Project Goal

The goal of **AcademyFlows** is to design a **scalable automation system for academic administrative processes** using Microsoft 365.

## Objectives

- Reduce manual administrative work
- Improve document organization
- Increase process transparency
- Enable scalable automation across faculties




