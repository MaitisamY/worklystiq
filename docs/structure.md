# 📁 Worklystiq Codebase Structure

This document outlines the folder structure for both the frontend and backend of the Worklystiq platform.

---

## 🖥 Frontend (`/frontend`)

- `public/`
  - `open-sans/` – font files
  - `*.png`, `favicon.ico` – icons and logos
  - `site.webmanifest` – PWA manifest
  - `worldcities.csv` – city dataset

- `src/`
  - `assets/`
    - `countries.json`
    - `notification.wav`
    - `worklystiq.png`
  - `components/Global/`
    - `Loader.jsx`
    - `Logout.jsx`
    - `EditableCostCell.jsx`
    - `OnboardedWrapper.jsx`
  - `config/`
    - `env.js`
  - `constants/`
    - `requirements.js`
  - `context/`
    - `NotificationProvider.jsx`
    - `MessageProvider.jsx`
  - `hooks/`
    - `useAnalytics.js`
    - `useOrderJs.js`
    - `useQuoteJs.js`
    - `useVectorJs.js`
    - `useSocket.js`
    - `useThrow.js`
  - `layout/`
    - `DashboardLayout.jsx`
    - `Sider.jsx`
    - `Section.jsx`
    - `Body.jsx`
  - `pages/`
    - `Overview.jsx`
    - `Orders.jsx`
    - `Quotes.jsx`
    - `Vectors.jsx`
    - `Invoices.jsx`
    - `PaymentSummary.jsx`
    - `Sales.jsx`
    - `Users.jsx`
    - `Notifications.jsx`
    - `Profile.jsx`
    - `Login.jsx`
    - `Signup.jsx`
    - `ResetPassword.jsx`
    - `Settings.jsx`
  - `routes/`
    - `config.routes.jsx`
    - `role.routes.jsx`
  - `services/`
    - `api.service.js`
    - `refresh.service.js`
  - `stores/`
    - `useAuthStore.js`
  - `utils/`
    - `playSound.util.js`
    - `formatting.util.js`
    - `activity.util.js`
    - `permission.util.js`
  - `App.jsx`, `main.jsx`, `ErrorBoundary.jsx`

---

## 🔧 Backend (`/backend`)

- `config/`
  - `db.js`

- `constants/`
  - `env.js`, `errors.js`, `notification.js`, `permissions.js`, `roles.js`, `status.js`

- `controllers/` – all route controller handlers

- `helpers/`
  - `fieldPopper.helper.js`
  - `formatter.helper.js`

- `jobs/`
  - `agenda.job.js`

- `lib/`
  - `api-auth.js`, `api-core.js`, `buy-link-auth.js`, `buy-link-signature.js`
  - `ipn.js`, `order.js`, `subscription.js`

- `logs/`
  - `exceptions.log`, `rejections.log`

- `middleware/`
  - `auth.middleware.js`

- `models/`
  - `Analytics.js`, `Invoice.js`, `Notification.js`, `Order.js`, `Quote.js`, `User.js`, `Vector.js`

- `provider/`
  - `twocheckout.provider.js`, `farmatter.helper.js`

- `public/`
  - `uploads/`, `index.html`, `cancel.html`, `success.html`, `*.png`

- `routes/`
  - `auth.routes.js`, `order.routes.js`, `quote.routes.js`, `vector.routes.js`
  - `invoice.routes.js`, `notification.routes.js`, `user.routes.js`
  - `analytics.routes.js`, `organization.routes.js`

- `services/` – core business logic per module

- `strategies/`
  - `jwt.strategy.js`, `local.strategy.js`

- `utils/`
  - `token.util.js`, `email.util.js`, `otp.util.js`, `codeGen.util.js`
  - `pdf.util.js`, `testJobs.util.js`, `templating.util.js`

- Root Files:
  - `.env`, `app.js`, `main.js`, `auth.js`, `socket.js`, `twocheckout.js`, `Dockerfile`, `package.json`