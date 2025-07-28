# 📁 Worklystiq Codebase Structure

This document outlines the full folder structure for both the frontend and backend of the Worklystiq project.

---

## 🖥 Frontend (`/frontend`)

```plaintext
/public
├── open-sans/                # Font files
├── favicon.ico, *.png        # Icons & logos
├── site.webmanifest          # PWA manifest
├── worldcities.csv           # Location data

/src
├── assets/                   # Static files
│   ├── countries.json
│   ├── notification.wav
│   └── worklystiq-logo.png
│
├── components/Global/        # Global UI components
│   ├── Loader.jsx
│   ├── Logout.jsx
│   ├── EditableCostCell.jsx
│   └── OnboardedWrapper.jsx
│
├── config/
│   └── env.js                # Environment-specific config
│
├── constants/
│   └── requirements.js       # Constants & enums
│
├── context/
│   ├── NotificationProvider.jsx
│   └── MessageProvider.jsx
│
├── hooks/                    # Custom hooks
│   ├── useAnalytics.js
│   ├── useOrderJs.js
│   ├── useVectorJs.js
│   ├── useSocket.js
│   └── useThrow.js
│
├── layout/                   # Layout components
│   ├── DashboardLayout.jsx
│   ├── Body.jsx
│   ├── Section.jsx
│   └── Sider.jsx
│
├── pages/                    # Page-level routes
│   ├── Orders.jsx
│   ├── Quotes.jsx
│   ├── Vectors.jsx
│   ├── Invoices.jsx
│   ├── PaymentSummary.jsx
│   ├── Sales.jsx
│   ├── Notifications.jsx
│   ├── Login.jsx
│   ├── Signup.jsx
│   ├── ResetPassword.jsx
│   ├── Overview.jsx
│   ├── Settings.jsx
│   └── Profile.jsx
│
├── routes/
│   ├── config.routes.jsx     # Route definitions
│   └── role.routes.jsx       # Role-based routing
│
├── services/
│   ├── api.service.js
│   └── refresh.service.js
│
├── stores/
│   └── useAuthStore.js       # Auth store
│
├── utils/
│   ├── playSound.util.js
│   ├── formatting.util.js
│   ├── permission.util.js
│   └── activity.util.js
│
├── App.jsx
├── main.jsx
└── ErrorBoundary.jsx
/config
└── db.js                      # MongoDB connection

/constants
├── env.js
├── errors.js
├── notification.js
├── permissions.js
├── roles.js
└── status.js

/controllers                  # Per-module controller files

/helpers
├── fieldPopper.helper.js
└── formatter.helper.js

/jobs
└── agenda.job.js             # Background jobs

/lib
├── api-auth.js
├── api-core.js
├── buy-link-*.js
├── ipn.js
├── order.js
└── subscription.js

/logs
├── exceptions.log
└── rejections.log

/middleware
└── auth.middleware.js        # Auth guards

/models
├── Analytics.js
├── Invoice.js
├── Notification.js
├── Order.js
├── Quote.js
├── User.js
└── Vector.js

/provider
├── twocheckout.provider.js
└── farmatter.helper.js

/public
├── uploads/
├── success.html
├── cancel.html
└── favicon.ico

/routes
├── auth.routes.js
├── order.routes.js
├── quote.routes.js
├── vector.routes.js
├── invoice.routes.js
├── notification.routes.js
├── user.routes.js
├── analytics.routes.js
└── organization.routes.js

/services                     # Business logic per module

/strategies
├── jwt.strategy.js
└── local.strategy.js

/utils
├── token.util.js
├── email.util.js
├── otp.util.js
├── codeGen.util.js
├── pdf.util.js
├── testJobs.util.js
└── templating.util.js

Root Files
├── app.js
├── main.js
├── auth.js
├── socket.js
├── twocheckout.js
├── Dockerfile
└── package.json