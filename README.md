# 🐙 GitHub Org Integration

> A lightweight **FastAPI** backend that connects your GitHub Organization to your infrastructure — handling OAuth login, real-time webhook ingestion, and org-wide analytics in one clean API.

---

## ✨ Features

- 🔐 **GitHub OAuth 2.0** — Secure login flow with encrypted token storage
- 🪝 **Webhook Receiver** — Verified, signature-checked GitHub event ingestion
- 📊 **Org Analytics** — Instant overview of repos, issues, teams & members
- 🍃 **MongoDB** — Async persistence via Motor
- ⚡ **FastAPI + Uvicorn** — High-performance async API

---

## 🗂️ Project Structure

```
github-org-integration/
├── main.py                  # FastAPI app entry point
├── requirements.txt
├── .env.example
└── app/
    ├── api/
    │   ├── auth.py          # GitHub OAuth routes
    │   ├── webhooks.py      # Webhook receiver
    │   └── analytics.py     # Org analytics endpoints
    ├── core/
    │   ├── config.py        # Pydantic settings
    │   └── security.py      # Token encryption & signature verification
    ├── db/
    │   └── mongo.py         # Async MongoDB connection
    ├── models/
    │   └── schemas.py       # Pydantic schemas
    ├── services/
    │   └── github_client.py # GitHub API HTTP client
    └── workers/             # Background workers
```

---

## 🚀 Quick Start

### 1. Clone & Install

```bash
git clone https://github.com/RoshanNandasana/GitHub-Organization-Level-Integration.git
cd GitHub-Organization-Level-Integration
pip install -r requirements.txt
```

### 2. Configure Environment

```bash
cp .env.example .env
# Fill in your values in .env
```

| Variable | Description |
|---|---|
| `GITHUB_CLIENT_ID` | Your GitHub OAuth App client ID |
| `GITHUB_CLIENT_SECRET` | Your GitHub OAuth App client secret |
| `GITHUB_WEBHOOK_SECRET` | Secret for verifying webhook payloads |
| `MONGO_URI` | MongoDB connection string |
| `ENCRYPTION_KEY` | 32-character key for token encryption |

### 3. Run the Server

```bash
uvicorn main:app --reload
```

API will be live at **`http://localhost:8000`**
Interactive docs at **`http://localhost:8000/docs`**

---

## 📡 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/health` | Health check |
| `GET` | `/auth/github/login` | Start GitHub OAuth flow |
| `GET` | `/auth/github/callback` | OAuth callback handler |
| `POST` | `/webhooks/github` | Receive GitHub webhook events |
| `GET` | `/analytics/org/{org_name}/overview` | Org stats overview |

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Framework | [FastAPI](https://fastapi.tiangolo.com/) |
| Server | [Uvicorn](https://www.uvicorn.org/) |
| Database | [MongoDB](https://www.mongodb.com/) via [Motor](https://motor.readthedocs.io/) |
| HTTP Client | [HTTPX](https://www.python-httpx.org/) |
| Config | [Pydantic Settings](https://docs.pydantic.dev/latest/concepts/pydantic_settings/) |

---

## 📄 License

MIT © [RoshanNandasana](https://github.com/RoshanNandasana)
