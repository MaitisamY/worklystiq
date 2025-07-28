# 📡 API Reference

All API endpoints use the prefix:  
**`/api/v1/`**

Authentication:  
- Most routes are protected via `sessionOrToken`
- Role-based guards (e.g. `roleGuard('ADMIN')`) apply where needed

---

## 🔐 Auth (`/api/v1/auth`)

| Method | Endpoint                        | Description                              |
|--------|---------------------------------|------------------------------------------|
| POST   | `/register`                     | Client signup                            |
| POST   | `/login`                        | Login with email/password                |
| POST   | `/register-from-inside`         | Register user internally (Admin)         |
| POST   | `/logout`                       | Logout                                   |
| GET    | `/check/status`                 | Basic system health                      |
| POST   | `/refresh-token`                | Refresh access token                     |
| GET    | `/check-auth`                   | Validate current session (optional auth) |
| POST   | `/check-password`               | Confirm current password                 |
| PATCH  | `/update-password`              | Update password                          |
| POST   | `/password-change-request`      | Request password change link             |
| POST   | `/otp-token-verify`             | OTP or token verification                |
| POST   | `/password-reset`               | Submit password reset                    |
| GET    | `/cleanup-tokens`               | Cleanup tokens (Admin only)              |
| GET    | `/verify-email/:token`          | Verify email address                     |

---

## 👤 Users (`/api/v1/user`)

| Method | Endpoint                       | Description                         |
|--------|--------------------------------|-------------------------------------|
| GET    | `/get`                         | Get all users (Admin/Salesman)      |
| GET    | `/get/profile`                 | Get logged-in user's profile        |
| PATCH  | `/update/profile`              | Update own profile                  |
| GET    | `/get/:id`                     | Get user by ID                      |
| PATCH  | `/approve/:id`                 | Approve a client                    |
| PATCH  | `/update/:id`                  | Update any user                     |
| PATCH  | `/activate-or-suspend/:id`     | Toggle user active status           |
| DELETE | `/delete/:id`                  | Delete user                         |
| PATCH  | `/onboard-the-client`          | Mark client as onboarded            |
| PATCH  | `/associate-salesman`          | Assign salesman to client           |
| PATCH  | `/disassociate-salesman`       | Remove salesman from client         |

---

## 📦 Orders (`/api/v1/order`)

| Method | Endpoint                          | Description                         |
|--------|-----------------------------------|-------------------------------------|
| GET    | `/get`                            | List all orders                     |
| POST   | `/create`                         | Create a new order                  |
| GET    | `/get/:id`                        | Get order by ID                     |
| PATCH  | `/update/:id`                     | Update order details                |
| PATCH  | `/update-cost/:id`                | Update cost                         |
| PATCH  | `/update-payment/:id`             | Update payment info                 |
| PATCH  | `/update-status/:id`              | Change status                       |
| PATCH  | `/update-details/:id`             | Update product-specific fields      |
| PATCH  | `/assign/admin/:id`               | Assign Admin                        |
| PATCH  | `/assign/salesman/:id`            | Assign Salesman                     |
| PATCH  | `/assign/designer/:id`            | Assign Designer                     |
| PATCH  | `/upload-files/:id`               | Upload design files                 |
| POST   | `/send-invoice`                   | Send invoice to client              |
| POST   | `/pay`                            | Mark as paid (manual)               |
| POST   | `/delete-bulk`                    | Delete multiple orders              |
| DELETE | `/delete/:id`                     | Delete a single order               |
| DELETE | `/delete/:id/attachment/:index`   | Remove a file from uploaded assets  |

---

## 💬 Quotes (`/api/v1/quote`)

Structure is identical to Orders.

---

## 🎨 Vectors (`/api/v1/vector`)

Structure is identical to Orders.

---

## 📨 Notifications (`/api/v1/notification`)

| Method | Endpoint                         | Description                         |
|--------|----------------------------------|-------------------------------------|
| GET    | `/get/count`                     | Count unread notifications          |
| GET    | `/get`                           | Get all notifications               |
| GET    | `/get/bell`                      | Get recent "bell" notifications     |
| POST   | `/create`                        | Create a notification               |
| POST   | `/custom-email/single`           | Send custom email                   |
| POST   | `/custom-email/multiple`         | Bulk email to multiple users        |
| PATCH  | `/mark-as-read`                  | Mark all as read                    |
| PATCH  | `/archive/:id`                   | Archive a specific notification     |
| DELETE | `/delete/:id`                    | Delete single notification          |
| DELETE | `/delete-all`                    | Delete all notifications            |

---

## 🧾 Invoices (`/api/v1/invoice`)

| Method | Endpoint                         | Description                         |
|--------|----------------------------------|-------------------------------------|
| GET    | `/get`                           | List all invoices                   |
| POST   | `/create`                        | Create invoice manually             |
| POST   | `/pay-invoices`                  | Client pays multiple invoices       |
| POST   | `/send/multiple`                 | Send batch invoices to clients      |
| PATCH  | `/mark-as-read/multiple`         | Mark batch as read                  |
| PATCH  | `/mark-as-paid/:id`              | Mark specific invoice paid          |

---

## 💳 Payment Summary (`/api/v1/payment-summary`)

| Method | Endpoint                          | Description                         |
|--------|-----------------------------------|-------------------------------------|
| GET    | `/get/payment-summaries`          | Get payment summaries (admin view)  |

---

## 📊 Analytics (`/api/v1/analytics`)

| Method | Endpoint                              | Description                        |
|--------|---------------------------------------|------------------------------------|
| GET    | `/get`                                | Get current analytics summary      |
| GET    | `/salesmen/monthly-sales`             | Get monthly sales by salesman      |

---

## 🏢 Organization (`/api/v1/organization`)

| Method | Endpoint                 | Description                         |
|--------|--------------------------|-------------------------------------|
| GET    | `/get`                   | Get organization settings           |
| PATCH  | `/update`                | Update org info (Admin only)        |
