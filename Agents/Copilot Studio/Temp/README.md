
---

```
███████╗███████╗██╗    ██████╗  ██████╗ ██╗     ██╗ ██████╗██╗   ██╗
██╔════╝██╔════╝██║    ██╔══██╗██╔═══██╗██║     ██║██╔════╝╚██╗ ██╔╝
█████╗  ███████╗██║    ██████╔╝██║   ██║██║     ██║██║      ╚████╔╝
██╔══╝  ╚════██║██║    ██╔═══╝ ██║   ██║██║     ██║██║       ╚██╔╝
██║     ███████║██║    ██║     ╚██████╔╝███████╗██║╚██████╗   ██║
╚═╝     ╚══════╝╚═╝    ╚═╝      ╚═════╝ ╚══════╝╚═╝ ╚═════╝   ╚═╝

██╗███╗   ██╗████████╗███████╗██╗
██║████╗  ██║╚══██╔══╝██╔════╝██║
██║██╔██╗ ██║   ██║   █████╗  ██║
██║██║╚██╗██║   ██║   ██╔══╝  ██║
██║██║ ╚████║   ██║   ███████╗███████╗
╚═╝╚═╝  ╚═══╝   ╚═╝   ╚══════╝╚══════╝
```

---

# 📘 FSI POLICY INTEL

> **AI-powered regulatory & policy intelligence for senior executives at Financial Services Institutions.**

---

## 🔍 Description

**FSI Policy Intel** is a Copilot Studio agent serving senior executives at Financial Services Institutions (FSIs). It monitors authoritative regulatory and policy information and delivers concise, executive-ready briefings focused on:

- 🏦 Financial regulation
- 💰 Tax policy
- 🌐 Trade and cross-border financial activity
- 🏛️ Monetary and fiscal policy
- 💳 Banking, capital markets, payments, fintech, and AI regulation

---

## ⚙️ How It Works — Operating Model

For every scheduled execution, the agent performs these steps in order:

| Step | Action |
|------|--------|
| 1 | Ingest updates from all configured RSS feed connectors *(last 7 days only)* |
| 2 | Normalize & classify each item |
| 3 | Deduplicate overlapping coverage |
| 4 | Apply materiality filters |
| 5 | Synthesize executive insights |
| 6 | Generate narrative briefings |
| 7 | Generate a consolidated executive summary table |
| 8 | Deliver full HTML briefing via **Email** and **Teams channel** |

> If no items meet thresholds, the agent outputs: *"No material regulatory or policy updates requiring executive attention."*

---

## 📋 Information Selection Criteria

The agent surfaces updates that signal:

- Regulatory or supervisory change
- Executive-level risk or opportunity
- Cross-border / trade impact
- Monetary, fiscal, or tax policy relevance
- Strategic horizon of **3–24 months**

---

## 📝 Executive Narrative Format

Every surfaced item includes:

| Field | Description |
|-------|-------------|
| **Headline** | Short, executive-ready title |
| **What Changed** | Clear description of the regulatory or policy shift |
| **Why It Matters** | Business impact and strategic relevance |
| **Who Is Affected** | Institutions, sectors, or geographies in scope |
| **Timeline** | Key dates and effective periods |
| **Source** | Canonical URL from the issuing authority |

---

## 📊 Consolidated Executive Summary Table

Every briefing ends with a summary table:

| Headline | URL | Policy Area | Jurisdiction | Impact Type | Who Is Affected | Timeline | Sensitivity Flag | Primary Source |
|----------|-----|-------------|--------------|-------------|-----------------|----------|-----------------|----------------|
| *...* | *...* | *...* | *...* | *...* | *...* | *...* | *...* | *...* |

Rules:
- One row per unique item
- URL maps directly to the headline
- Only items from the **last 7 days**
- Sensitivity flag included only when required

---

## 📬 Delivery Channels

### Email
- Connector: **Send an email (V2)**
- HTML-formatted body with headings, emojis, bullet lists, and `<table>` summary
- No plaintext emails

### Microsoft Teams
- Connector: **Post message in a chat or channel**
- Same full HTML briefing as email
- No attachments — no plaintext fallback

---

## 🎨 Formatting Rules

### Emoji Usage — Section Headers Only

| Emoji | Usage |
|-------|-------|
| 📘 | Email / Teams title header |
| 🔹 | Section headers |
| 🚨 | Immediate executive attention |
| ⚠️ | Emerging risk |
| 💡 | Strategic opportunity |
| 📊 | Executive summary table header |

> Emojis are **not** embedded within sentences.

### Briefing Subject / Title Format

```
📘 FSI Policy Intel Brief — [Daily | Weekly | Monthly]
```

### HTML Body Structure

1. Header with title emoji
2. Narrative briefing sections
3. Escalation flags (🚨 / ⚠️ / 💡)
4. 📊 Executive summary table

---

## 🔄 Continuous Improvement

The agent is always optimized for:

- Executive readability
- Reduced noise
- Consistent format across runs
- Fail-safe formatting for external forwarding
- Precision and materiality filtering

---

## ⚠️ Disclaimer

> This briefing is for informational purposes only and does not constitute legal, tax, or investment advice. Recipients should consult qualified advisors before taking action based on this material.

---

*Powered by Microsoft Copilot Studio · Built for Financial Services*
