<div align="center">

<img src="https://somos.tech/favicon.ico" width="48" alt="SOMOS.tech" />

# SOMOS.tech Labs

**Hands-on tech labs for builders who learn by doing.**

[![Labs](https://img.shields.io/badge/labs-somos.tech%2Fprograms%2Flabs-00D4FF?style=flat-square)](https://somos.tech/programs/labs)
[![Community](https://img.shields.io/badge/community-join%20SOMOS-A855F7?style=flat-square)](https://somos.tech)
[![License](https://img.shields.io/badge/license-MIT-22c55e?style=flat-square)](LICENSE)

</div>

---

## Tracks

| Track | Status | Description |
|-------|--------|-------------|
| ⚡ **[Vibe Coding × Azure](./vibe-coding/)** | 🟢 Active | Ship real apps to the cloud. Hands-on Azure labs from zero to deployed. |
| 🤖 **[AI Agents](./ai-agents/)** | 🔜 Coming Soon | Build autonomous agents that reason, plan, and use tools. |
| 🔌 **[MCP Servers](./mcp-servers/)** | 🔜 Coming Soon | Build Model Context Protocol servers that give AI models access to your APIs. |

---

## ⚡ Vibe Coding × Azure

> *Deploy real projects to the cloud on Azure Free Tier — no credit card tricks.*

| Lab | Folder | Time | Level |
|-----|--------|------|-------|
| ☁️ **Deploy to Azure App Service** | [`vibe-coding/azure/`](./vibe-coding/azure/) | 45 min | Beginner |
| 🗄️ Add a Database with Cosmos DB | *coming soon* | 60 min | Beginner |
| 🔐 Secure Secrets with Key Vault | *coming soon* | 30 min | Intermediate |

### Lab 1 — Deploy to Azure App Service

Fork this repo, get a live `.azurewebsites.net` URL, and set up full CI/CD in under 45 minutes.

**Everything you need is inside [`vibe-coding/azure/`](./vibe-coding/azure/)** — starter code + a pre-built GitHub Actions workflow that auto-deploys on every push.

#### Quick Start (3 steps)

**1 — Fork this repo**

Click **Fork** at the top right. This gives you your own copy to deploy from.

**2 — Create a free Azure App Service**

```
portal.azure.com → + Create a resource → App Service
  Runtime:  Node 20 LTS  (or HTML)
  OS:       Linux
  Region:   East US
  Plan:     Free F1  ← important!
```

Once created, click **Download publish profile** on the App Service Overview page.

**3 — Add two values to your GitHub fork**

In your fork: **Settings → Secrets and variables → Actions**

| Kind | Name | Value |
|------|------|-------|
| Secret | `AZURE_WEBAPP_PUBLISH_PROFILE` | Paste the full XML from the `.PublishSettings` file |
| Variable | `AZURE_WEBAPP_NAME` | Your App Service name, e.g. `yourname-somos-lab` |

Now push any commit to `main` — GitHub Actions deploys automatically. ✅

Your live URL:
```
https://YOUR-APP-NAME.azurewebsites.net
```

---

## Repo Structure

```
labs/
├── vibe-coding/
│   └── azure/                  ← Lab 1: Azure App Service starter + workflow
│       ├── index.html
│       └── .github/
│           └── workflows/
│               └── azure-webapps.yml
├── ai-agents/                  ← Coming soon
└── mcp-servers/                ← Coming soon
```

---

## Customize Your App

Edit `index.html` in `vibe-coding/azure/` and push:

```bash
git add .
git commit -m "feat: customize my landing page"
git push origin main
```

Changes go live within ~60 seconds. Watch it in the **Actions** tab.

---

## Node.js / Build Step?

The included workflow automatically detects a `package.json` and runs `npm ci && npm run build --if-present`.

If your build outputs to a folder (e.g. `dist/`), uncomment one line in the workflow:

```yaml
# package: './dist'
```

---

## Share Your Win

Deployed? Drop your `.azurewebsites.net` URL in [#labs on SOMOS.tech](https://somos.tech) — we celebrate every first cloud deployment. 🎉

---

## What's Next

| | |
|---|---|
| 📚 **Full lab guide** | [somos.tech/programs/labs](https://somos.tech/programs/labs) |
| 💬 **Community** | [somos.tech](https://somos.tech) |
| 🐛 **Issues / questions** | [github.com/somos-tech/labs/issues](https://github.com/somos-tech/labs/issues) |

---

<div align="center">

Built with 💜 by the [SOMOS.tech](https://somos.tech) community

</div>
