# 🔁 Worklystiq Workflows

This document describes the key workflows for all user roles in the system — from registration to order completion, including Quotes, Vectors, Invoices, and Approvals.

---

## 🧩 Roles

- **ADMIN** – Manages users, assigns tasks, reviews progress, handles invoices
- **CLIENT** – Places orders, receives files, requests edits, pays
- **SALESMAN** – Can register and manage their clients
- **DESIGNER** – Uploads designs for assigned tasks
- **MANAGER** – Reviews, adjusts, or replaces designer files before processing

---

## 📝 Client Registration Flow

1. **Client registers**
   - Enters: name, email, phone, password
   - Account is set to `PENDING` approval

2. **Admin approves**
   - Admin reviews and approves the user
   - Status becomes `ACTIVE + APPROVED`
   - Now allowed to login

---

## 🧾 Order / Quote / Vector Workflow

All 3 modules (Orders, Quotes, Vectors) follow the same multi-stage process.

### 🔹 1. Creation
- **Who**: Client, Admin, or Salesman
- **Action**: Creates an order with name, description, design notes, files
- **Initial Status**: `RECEIVED`

---

### 🔹 2. Assignment (Admin)
- Admin selects:
  - **Salesman** (if client is not yet assigned one)
  - **Designer**
  - **Sets Cost**
- **Next Status**: `IN PROGRESS`

---

### 🔹 3. Design Phase (Designer)
- Assigned **designer sees order** in dashboard
- Uploads design files
- Files are attached and previewable
- **Next Status**: `IN REVIEW`

---

### 🔹 4. Review Phase (Manager)
- Manager reviews uploaded designs:
  - Can **delete**, **replace**, or **add** files
- Once finalized:
  - **Updates status** → `PROCESSED`

---

### 🔹 5. Processing & Invoice (Admin)
- Admin clicks **Process**
- Automatically:
  - Creates invoice
  - Sends email to client with link
  - Updates status → `RELEASED`

---

### 🔹 6. Review & Payment (Client)
- Client opens released file
- Options:
  - ✅ Approve and **pay** → status becomes `COMPLETED`
  - 📝 **Request edits** → status becomes `EDIT REQUEST`

---

## 🔔 Notifications & Emails

Triggered automatically at key steps:

| Action                      | Notifies              |
|----------------------------|-----------------------|
| Client registers           | Admin (email + in-app)|
| Order assigned             | Salesman, Designer    |
| File uploaded              | Manager               |
| Processed by manager       | Admin                 |
| Invoice generated          | Client (email + in-app)|
| Edit request submitted     | Admin, Designer       |
| Payment completed          | Admin                 |

> All notifications use Socket.IO and have sound in frontend.

---

## 📈 Sales Reports & Payment Summary

- **Admins** view:
  - Monthly Sales grouped by Salesman and Designer
  - Filterable by history tab

- **Payment Summary**:
  - Nested table per client
  - Shows unpaid/paid status
  - Clickable to jump to invoices

---

## 💸 Invoice Actions

- Admin can:
  - Manually mark as paid
  - Resend multiple invoices

- Client can:
  - Pay via 2Checkout
  - Receive email and dashboard link
