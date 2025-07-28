# 📁 Folder Structure

## Frontend

src/
├── assets/ # Static files (logos, icons, etc.)
├── components/ # Reusable UI components
├── config/ # Axios / API configs
├── constants/ # Role types, enums, etc.
├── context/ # Global state/context providers
├── hooks/ # Custom hooks
├── layout/ # Base layouts (e.g., SidebarLayout)
├── pages/ # Route-level components
├── routes/ # Route configs
├── services/ # API calls
├── stores/ # State (will move to TanStack Query soon)
├── utils/ # Utility functions


## Backend

backend/
├── config/ # DB and global config
├── constants/ # Role enums, status mappings
├── controllers/ # Route handlers
├── helpers/ # Utility functions
├── jobs/ # Cron tasks
├── lib/ # Socket and reusable services
├── logs/ # Winston logs
├── middleware/ # Auth, permissions, errors
├── models/ # Mongoose schemas
├── provider/ # Third-party (2Checkout, etc.)
├── routes/ # Express routers
├── services/ # Core logic
├── strategies/ # Auth strategies
├── utils/ # Formatters, validators