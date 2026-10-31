# 🤖 WhatsApp AI Reporting Assistant

> Role-based AI assistant delivered via WhatsApp — answers operational queries, generates PDF reports, and sends live-data alerts. Built for a poultry enterprise serving CEO to farm-level roles.

---

## 🎯 Problem Solved

Management needed real-time operational data (sales, farm performance, hatchery stats) without logging into dashboards. Built a conversational AI that answers in WhatsApp — the app everyone already uses.

---

## 🏗️ System Architecture

```
User (WhatsApp Message)
        ↓
WhatsApp Business API
        ↓
n8n Webhook Trigger
        ↓
Role Detection (CEO / GM / Sales / Farm)
        ↓
Live Data Query (PostgreSQL / MongoDB / APIs)
        ↓
Claude API — Context-aware response generation
        ↓
┌───────────────────────────────┐
│  Text Reply  │  PDF Report   │  Scheduled Alert  │
│  (instant)   │  (PDFShift)   │  (threshold-based) │
└───────────────────────────────┘
        ↓
WhatsApp Delivery
```

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Messaging | WhatsApp Business API |
| Orchestration | n8n (self-hosted) |
| AI Model | Claude API (Anthropic) |
| PDF Generation | PDFShift |
| Backend | Python + FastAPI |
| Databases | PostgreSQL, MongoDB |
| Auth | Role-based access (JWT) |

---

## ⚡ Key Features

- **Role-based access control** — 8 roles: CEO, GM, Sales, Broiler, Breeder, Hatchery, Feedmill, Farm
- **Live data queries** — pulls real-time data from backend on each message
- **Text + image input** — handles photos from farms (disease detection context)
- **On-demand PDF reports** — generated and sent directly in WhatsApp
- **Scheduled alerts** — auto-notifies when KPIs breach thresholds
- **Context-aware replies** — each role sees only their relevant data

---

## 💬 Example Interactions

```
CEO asks:    "What's today's total sales revenue?"
Bot replies: "Today's revenue: PKR 2.4M (↑12% vs yesterday)
              Top region: Karachi — PKR 890K
              [Tap for full PDF report]"

Farm Manager asks: "Mortality rate this week?"
Bot replies: "Shed 3 mortality: 1.2% (within normal range)
              Shed 7 mortality: 3.8% ⚠️ (above 3% threshold)
              Recommend: vet inspection for Shed 7"
```

---

## 🔒 Note

This is a **proprietary production system**. This repo documents the architecture, role-access design, and workflow logic. No internal data or credentials are included.

---

## 📁 What's In This Repo

```
whatsapp-ai-assistant/
├── architecture/
│   ├── system-diagram.png       — Full system flow
│   ├── role-access-matrix.md    — Who sees what
│   └── n8n-workflow-overview.png
├── docs/
│   ├── api-endpoints.md
│   └── alert-logic.md
├── demo/
│   └── sample-interactions.md   — Sanitized example conversations
└── README.md
```

---

*Built by [Syed Fahad Fazal](https://linkedin.com/in/syed-fahad-fazal) — AI Engineer @ Poulta Inc*
