# 🚀 Worklystiq Deployment Guide

This document explains how to deploy Worklystiq on a **Hostinger VPS** using **Coolify** with full CI/CD integration via **GitHub Deploy Keys**. This method is completely automated after setup, using Docker, MongoDB, and GitHub.

---

## 📦 What You Need

- ✅ A [Hostinger VPS](https://www.hostinger.com/)
- ✅ A registered domain (or subdomain of an existing one)
- ✅ A [GitHub](https://github.com/) repo for your frontend/backend project
- ✅ A self-hosted or cloud [Coolify](https://coolify.io/) instance

---

## 1️⃣ Buy VPS & Setup Domain

1. **Create a Hostinger account**
2. Purchase a **VPS plan**
3. Choose **Ubuntu or Debian** as the OS (recommended)
4. Install Coolify (or use their cloud)

   → [Coolify self-hosting instructions](https://docs.coolify.io/getting-started/self-host)

---

## 2️⃣ Configure Domain or Subdomain

1. Go to your domain provider (e.g., Namecheap, GoDaddy, Hostinger DNS)
2. Create:
   - `A record` pointing to your VPS’s **IPv4 address**
   - `AAAA record` pointing to your VPS’s **IPv6 address**

Example:

| Type  | Name         | Value           |
|-------|--------------|-----------------|
| A     | `worklystiq` | `123.45.67.89`  |
| AAAA  | `worklystiq` | `2606:abcd:...` |

✅ You can use `app.yourdomain.com`, `api.yourdomain.com`, etc.

---

## 3️⃣ Create Deploy Key in Coolify

1. Open your **Coolify dashboard**
2. Go to **Deploy Keys** in the left sidebar
3. Click **Add New Key**
4. Copy the **public key** (you'll use this in GitHub later)

---

## 4️⃣ Setup MongoDB in Coolify

1. Go to **Projects** → Click **Create Project**
2. Inside the project, click **+ Add Resource**
3. Choose **MongoDB**
4. Expose it publicly:
   - Assign a custom port like `27017` or leave default
   - Enable "Expose to the internet"
5. Click **Create**
6. Once running, note your:
   - Connection string (e.g. `mongodb://...`)
   - Port

---

## 5️⃣ Add Deploy Key to GitHub

1. Open your project on GitHub
2. Go to: `Settings > Deploy keys`
3. Click **Add deploy key**
   - Title: `Coolify`
   - Paste the **public key** from step 3
   - ✅ Check "Allow write access"
4. Save

---

## 6️⃣ Add GitHub Repo as a Coolify Resource

1. Go back to Coolify → Your **Project**
2. Click **+ Add Resource**
3. Choose **Git Repository**
4. Paste your GitHub repo URL
5. Select:
   - Branch: `main` or `production`
   - Project type: `Docker Compose` or `Dockerfile`
6. Click **Create Resource**

---

## 7️⃣ Configure Build & Runtime

Once the resource is created:

### 🔧 General Section

- Set:
  - **Project name**
  - **Dockerfile path** (if not root)
  - **Build & Start commands** (optional)

### 🔐 Environment Variables

Add environment variables required by backend/frontend:

Copy from `.env.example` file and replace with your configs.
