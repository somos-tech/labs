<div align="center">

# ☁️ Lab 1 — Deploy to Azure App Service

**Vibe Coding × Azure · Beginner · 45 minutes**

[![Azure](https://img.shields.io/badge/Azure-App%20Service-0078D4?style=flat-square&logo=microsoftazure)](https://azure.microsoft.com/products/app-service/)
[![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-2088FF?style=flat-square&logo=githubactions)](https://github.com/features/actions)
[![Cost](https://img.shields.io/badge/cost-Free%20F1%20tier-22c55e?style=flat-square)](https://azure.microsoft.com/pricing/details/app-service/linux/)

</div>

---

## What you'll build

By the end of this lab you'll have:

- 🌐 A **live public URL** — `yourname.azurewebsites.net`
- ⚡ A **GitHub Actions pipeline** that redeploys every time you push
- ☁️ Real Azure infrastructure provisioned from scratch — for free

---

## Prerequisites

Before you start:

- ✅ [Azure free account](https://azure.microsoft.com/free/) — new accounts get $200 credit; F1 tier costs $0
- ✅ [GitHub account](https://github.com/join)
- ✅ [VS Code](https://code.visualstudio.com/) + [Git](https://git-scm.com/downloads)

---

## Setup (3 steps, ~10 min)

### Step 1 — Fork this repo

Click **Fork** at the top of the page. This creates your own copy to deploy from.

Then clone it:

```bash
git clone https://github.com/YOUR-USERNAME/labs.git
cd labs/vibe-coding/azure
code .
```

### Step 2 — Create a free Azure App Service

1. Sign in at [portal.azure.com](https://portal.azure.com)
2. Click **+ Create a resource** → search **App Service** → **Create**
3. Fill in:

   | Field | Value |
   |-------|-------|
   | Resource Group | Create new → `somos-lab-rg` |
   | Name | Something unique, e.g. `yourname-somos-lab` |
   | Publish | Code |
   | Runtime stack | Node 20 LTS *(or Static HTML)* |
   | OS | Linux |
   | Region | East US |
   | Pricing plan | **Free F1** ← select "Dev/Test" to find it |

4. Click **Review + create** → **Create** (~60 seconds)
5. On the App Service Overview page, click **Download publish profile** and save the file

### Step 3 — Add your Azure credentials to GitHub

In your forked repo: **Settings → Secrets and variables → Actions**

**Secrets tab:**
| Name | Value |
|------|-------|
| `AZURE_WEBAPP_PUBLISH_PROFILE` | Open the `.PublishSettings` file and paste the entire XML content |

**Variables tab:**
| Name | Value |
|------|-------|
| `AZURE_WEBAPP_NAME` | Your App Service name (e.g. `yourname-somos-lab`) |

> ⚠️ Keep the publish profile private. Never commit it to the repo.

---

## Deploy

Push any commit to `main` — the workflow deploys automatically:

```bash
# Edit index.html, then:
git add .
git commit -m "feat: my first cloud deployment"
git push origin main
```

Watch it in the **Actions** tab. Your site goes live in ~60 seconds at:

```
https://YOUR-APP-NAME.azurewebsites.net
```

---

## Files in this folder

```
azure/
├── index.html                       ← Edit this — it's your live website
└── .github/
    └── workflows/
        └── azure-webapps.yml        ← Pre-built deploy workflow (don't need to touch it)
```

---

## Customise your page

Open `index.html` and make it yours:

```html
<h1>Hello from YOUR NAME 🚀</h1>
<p>My first cloud deployment, powered by Azure.</p>
```

Every push to `main` triggers a new deploy. CI/CD is live from day one.

---

## Have a Node.js / build step?

The workflow auto-detects `package.json` and runs `npm ci && npm run build --if-present`.

If your output goes to a `dist/` folder, uncomment one line in `.github/workflows/azure-webapps.yml`:

```yaml
# package: './dist'
```

---

## ✅ Done? Share it!

Drop your `.azurewebsites.net` URL in [#labs on SOMOS.tech](https://somos.tech) — we celebrate every first deployment. 🎉

Then continue the track → **[Lab 2: Add a Database with Cosmos DB](../cosmos-db/)** *(coming soon)*

---

<div align="center">

[← Vibe Coding track](../) · [Full interactive guide](https://somos.tech/programs/labs/vibe-coding/azure-app-service) · [All tracks](../../)

</div>
