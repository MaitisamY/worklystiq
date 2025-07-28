# 📡 API Reference (Core)

All requests require a valid bearer token unless stated.

## 🔐 Auth
- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/auth/me`

## 👤 Users
- `POST /api/users/create` (Admin only)
- `GET /api/users/list` (Admin/Salesman)
- `PATCH /api/users/:id/approve`

## 🛒 Orders / Quotes / Vectors
- `POST /api/orders`
- `GET /api/orders/:id`
- `PATCH /api/orders/:id/status`

## 💳 Invoices
- `GET /api/invoices/client`
- `PATCH /api/invoices/:id/pay`

...

→ Will expand with real endpoints as you finalize.