# ⚡ Conditional Routing with IF & Switch Nodes

[![n8n workflow](https://img.shields.io/badge/n8n-Workflow-orange.svg)](https://n8n.io)
[![Sequence](https://img.shields.io/badge/Sequence-%2303-blue.svg)](#)
[![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-green.svg)](#)
[![Status](https://img.shields.io/badge/Status-Production--Ready-brightgreen.svg)](#)

> **Workflow Sequence #03** in the [Maheen Azhar n8n Workflow Collection](https://github.com/maheenazhar/n8n-workflows-collection).

---

## 📖 Overview

Demonstrates multi-branch conditional routing based on sheet data, directing records through distinct messaging pipelines depending on logical expressions.

### 🎯 Key Use Case
Dispatching tailored email alerts based on customer priority, ticket severity, or transaction status.

---

## 🏗️ Architecture & Flow

```mermaid
graph TD
  N0_Google_Sheets_Trigger["Google Sheets Trigger<br><i>(googleSheetsTrigger)</i>"]
  N1_If["If<br><i>(if)</i>"]
  N2_Send_a_message["Send a message<br><i>(gmail)</i>"]
  N3_Send_a_message1["Send a message1<br><i>(gmail)</i>"]
  N4_Send_a_message2["Send a message2<br><i>(gmail)</i>"]
  N5_Send_a_message3["Send a message3<br><i>(gmail)</i>"]
  N0_Google_Sheets_Trigger --> N1_If
  N1_If -->|branch 1| N2_Send_a_message
  N1_If -->|branch 2| N3_Send_a_message1
```

---

## 🧩 Nodes in this Workflow

| # | Node Name | Type | Version |
|---|-----------|------|---------|
| 1 | **Google Sheets Trigger** | `n8n-nodes-base.googleSheetsTrigger` | v1 |
| 2 | **If** | `n8n-nodes-base.if` | v2.3 |
| 3 | **Send a message** | `n8n-nodes-base.gmail` | v2.2 |
| 4 | **Send a message1** | `n8n-nodes-base.gmail` | v2.2 |
| 5 | **Send a message2** | `n8n-nodes-base.gmail` | v2.2 |
| 6 | **Send a message3** | `n8n-nodes-base.gmail` | v2.2 |

---

## 🔑 Prerequisites & Credentials

Before running this workflow, ensure you have the following configured in your n8n environment:

- [ ] **Google Sheets credential**
- [ ] **Gmail credential**
- [ ] **Spreadsheet containing conditional criteria columns (e.g. status, priority)**

> [!NOTE]
> All credentials are decoupled from this export file for security. When importing into your n8n workspace, re-assign your local credentials in the respective node configuration panels.

---

## 🚀 Setup & Installation

1. **Clone or Download:**
   ```bash
   git clone https://github.com/maheenazhar/n8n-03-if-switch-nodes.git
   cd n8n-03-if-switch-nodes
   ```
2. **Import into n8n:**
   - Open your n8n canvas.
   - Click the top-right menu `...` -> **Import from File**.
   - Select `workflow.json` from this repository.
   - *(Alternative)*: Open `workflow.json`, copy the entire JSON contents, and paste directly (`Ctrl+V`) onto the n8n canvas.
3. **Configure Credentials:**
   - Open each integration node marked with a red credential prompt.
   - Select or configure your accounts (e.g., Google OAuth, Groq API, Supabase, SMTP).
4. **Activate / Test:**
   - Click **Test step** or **Execute Workflow** to verify end-to-end functionality.
   - Toggle the workflow to **Active** for live production use.

---

## 📄 File Structure

```
03-if-switch-nodes/
├── workflow.json   # Full exportable n8n workflow definition
├── README.md       # Comprehensive documentation and architecture
└── .gitignore      # Standard Git exclusions
```

---

## 👤 Author & Repository

- **Author:** [Maheen Azhar](https://github.com/maheenazhar)
- **Workflow ID:** `6bQe7Ysnv3qu4UNa`
- **Created Date:** `2026-10-07 19:46:46.271`
- **Last Modified:** `2026-10-07 20:20:22.149`
- **Repository:** [`https://github.com/maheenazhar/n8n-03-if-switch-nodes`](https://github.com/maheenazhar/n8n-03-if-switch-nodes)

---

*Part of the [n8n Workflows Collection](https://github.com/maheenazhar/n8n-workflows-collection) by Maheen Azhar.*
