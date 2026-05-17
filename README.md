<div align="center">

# 🛡️ Aegis Pro v1

### Autonomous Supply Chain Crisis Management

[![License: MIT](https://img.shields.io/badge/License-MIT-teal.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![Gemini](https://img.shields.io/badge/Gemini-3%20Flash%20Preview-4285F4.svg)](https://ai.google.dev/)
[![Veea](https://img.shields.io/badge/Infra-Veea%20Lobster%20Trap-1D9E75.svg)](https://www.veea.com/)
[![Colab](https://img.shields.io/badge/Platform-Google%20Colab-F9AB00.svg)](https://colab.research.google.com/)
[![GitHub Pages](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-222222.svg)](https://benny-tang.github.io/aegis-pro-v1)
[![Hackathon](https://img.shields.io/badge/TechEx-San%20Jose%202026-553AB7.svg)](https://lablab.ai/)

**Signal to autonomous action in under 60 seconds.**

### 🌐 [LIVE DEMO → benny-tang.github.io/aegis-pro-v1](https://benny-tang.github.io/aegis-pro-v1)

> No API key needed — click Launch Pipeline and watch all 8 agents fire live.

Built for [LabLab.ai TechEx San Jose 2026](https://lablab.ai/)
Track 1 (Veea) · Track 2 (Google AI Studio) · Track 4 (Data & Intelligence)

</div>

---

## 📌 Table of Contents

- [Live Demo](#-live-demo)
- [Overview](#-overview)
- [Key Features](#-key-features)
- [The 8-Agent Pipeline](#-the-8-agent-pipeline)
- [Architecture](#-architecture)
- [Tech Stack](#-tech-stack)
- [Quickstart](#-quickstart)
- [Configuration](#-configuration)
- [Business Case](#-business-case)
- [Deployment](#-deployment)
- [Project Structure](#-project-structure)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [Team](#-team)
- [License](#-license)

---

## 🌐 Live Demo

**Primary URL:** https://benny-tang.github.io/aegis-pro-v1

Open in any browser — no installation, no API key required.

| Mode | How to use |
|---|---|
| **Demo mode** | Leave API key blank — full mock pipeline runs instantly |
| **Live mode** | Paste your Gemini API key — real Gemini 3 Flash calls fire |

**4 crisis scenarios available:**
- Strait of Hormuz Disruption
- Suez Canal Blockage
- Taiwan Strait Tension
- Supplier Pandemic Shutdown

---

## 🧭 Overview

Aegis Pro v1 is an **8-agent autonomous AI swarm** that detects, analyses, forecasts, simulates, decides, alerts, executes, and synthesises supply chain crisis responses — end to end, without human intervention.

Traditional supply chain monitoring tools stop at alerting. Aegis closes the full loop: from live marine traffic signal to ERP workflow trigger, with a quantified USD savings figure attached to every recommended action.

> **Demo scenario:** Strait of Hormuz disruption — 3 VLCCs rerouted, war risk premiums +40%.
> **Aegis response time:** 60 seconds.
> **Estimated savings triggered:** $1.65M (vs. $1.7M do-nothing cost — 97% avoidance rate).

---

## ✨ Key Features

| Feature | Description |
|---|---|
| **8-Agent Swarm** | Signal → Intelligence → Forecast → Simulation → Decision → Alert → Execution → Synthesis |
| **Gemini 3 Flash Preview** | Primary LLM — multi-turn reasoning, structured JSON mode, streaming |
| **Gemini 2.5 Flash** | Fallback + lighter agents (smart model routing saves free tier quota) |
| **ARIMA + XGBoost** | ML ensemble forecaster — 14-day horizon, composite risk scoring |
| **Marine Scraper** | Live gCaptain + TradeWinds ingestion with simulated fallback |
| **Multi-turn Reasoning** | Decision Agent uses Gemini iterative refinement |
| **Confidence Calibration** | Data freshness decay applied to all agent confidence scores |
| **Synthesis Agent** | Cross-validates all 7 agents for contradictions before execution |
| **Live Investor UI** | Dark ops dashboard — agents fire one by one with live terminal stream |
| **Plotly Dashboard** | 4-panel risk dashboard in Colab: forecast, scenarios, savings, scores |
| **Veea Edge Export** | Production push to Veea Lobster Trap edge node |
| **Speechmatics Voice** | TTS-ready voice alert text in Alert Agent output |
| **Rate Limit Guard** | Auto-retry with extracted wait time + smart model routing |
| **LIVE_MODE Guard** | `LIVE_MODE=False` by default — zero API credits in dev/test |
| **Full Audit Trail** | Every autonomous action logged with rationale and timestamp |

---

## 🤖 The 8-Agent Pipeline

```
┌─────────────┐    ┌───────────────┐    ┌──────────────┐    ┌──────────────┐
│  1. SIGNAL  │───▶│ 2. INTELLIGENCE│───▶│ 3. FORECAST  │───▶│ 4. SIMULATION│
│             │    │               │    │              │    │              │
│ Marine live │    │ Geopolitical  │    │ ARIMA+XGBoost│    │ 3-scenario   │
│ gCaptain    │    │ root cause    │    │ 14-day ML    │    │ Monte Carlo  │
│ TradeWinds  │    │ analysis      │    │ ensemble     │    │ probability  │
└─────────────┘    └───────────────┘    └──────────────┘    └──────┬───────┘
                                                                    │
┌─────────────┐    ┌───────────────┐    ┌──────────────┐    ┌──────▼───────┐
│ 8. SYNTHESIS│◀───│  7. EXECUTION │◀───│  6. ALERT    │◀───│ 5. DECISION  │
│             │    │               │    │              │    │              │
│ Cross-agent │    │ SAP ERP + 3PL │    │ Slack/Email/ │    │ Gemini 3     │
│ validation  │    │ workflow auto │    │ Voice alerts │    │ Flash multi- │
│ risk score  │    │ + audit trail │    │ Speechmatics │    │ turn reason  │
└─────────────┘    └───────────────┘    └──────────────┘    └──────────────┘
```

### Smart model routing (saves free tier quota)

| Agent | Model | Reason |
|---|---|---|
| Signal, Intelligence, Forecast, Simulation, Alert, Execution | `gemini-2.5-flash` | Higher RPM on free tier |
| Decision, Synthesis | `gemini-3-flash-preview` | Needs deepest reasoning |

---

## 🏗️ Architecture

```
                    ┌─────────────────────────────────────┐
                    │         Aegis Pro v1 Stack           │
                    │                                      │
                    │  Live UI (GitHub Pages / AI Studio)  │
                    │         ↓                            │
                    │  8-Agent Swarm (Gemini 3 Flash)      │
                    │         ↓                            │
                    │  ARIMA + XGBoost Forecaster          │
                    │         ↓                            │
                    │  Marine Scraper (gCaptain/TradeWinds)│
                    │         ↓                            │
                    │  Veea Lobster Trap Edge Export       │
                    └─────────────────────────────────────┘
                                      ↓
              ┌──────────────────────────────────────────────┐
              │                  Outputs                      │
              │  SAP ERP · Freight Broker · Slack/Email      │
              │  Speechmatics TTS · Veea edge · Dashboard    │
              └──────────────────────────────────────────────┘
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Primary LLM** | Google Gemini 3 Flash Preview (AI Studio) |
| **Secondary LLM** | Google Gemini 2.5 Flash (lighter agents + fallback) |
| **ML Forecasting** | ARIMA(2,1,2) via statsmodels + XGBoost ensemble |
| **Data Ingestion** | gCaptain + TradeWinds (BeautifulSoup4 + lxml) |
| **Live UI** | Vanilla HTML/CSS/JS — dark ops theme |
| **Colab Dashboard** | Plotly + Matplotlib |
| **Edge Infra** | Veea Lobster Trap (TerraFabric) |
| **Voice Alerts** | Speechmatics TTS |
| **Hosting** | GitHub Pages (primary) · Google AI Studio (secondary) |
| **Runtime** | Python 3.10+ · Google Colab |

---

## 🚀 Quickstart

### Option A — Live demo (no install)

Open https://benny-tang.github.io/aegis-pro-v1 in any browser.
Leave API key blank. Click Launch Pipeline.

### Option B — Google Colab

1. Open `Aegis_Pro_v1_LIVE_UI.ipynb` in Google Colab
2. Run Cell 1 (install packages)
3. Run Cell 2 (paste API keys)
4. Run Cell 3 (launch UI + pipeline)

### Option C — Local Flask server

```bash
git clone https://github.com/Benny-Tang/aegis-pro-v1.git
cd aegis-pro-v1
pip install -r requirements.txt
export GEMINI_API_KEY=your_key_here
python app.py
# Open http://localhost:8080
```

---

## ⚙️ Configuration

| Variable | Description | Required |
|---|---|---|
| `GEMINI_API_KEY` | Google AI Studio API key | Live mode |
| `SPEECHMATICS_API_KEY` | Speechmatics TTS key | Voice alerts |
| `VEEA_API_KEY` | Veea Lobster Trap key | Production edge |
| `LIVE_MODE` | `True` = live calls · `False` = mock (default) | Always |
| `GEMINI_MODEL` | Primary model string | Always |
| `SCAN_INTERVAL_SECONDS` | Auto-scan interval (default 300) | Optional |

> ⚠️ Never commit API keys. Use environment variables or Colab secrets.

---

## 💰 Business Case

### Per-event savings (single Hormuz-scale disruption)

| Priority | Action | Est. Savings | Risk | Mode |
|---|---|---|---|---|
| P1 | Buffer inventory activation (24h) | $850,000 | LOW | Autonomous |
| P2 | Cape route capacity pre-booking (48h) | $420,000 | MEDIUM | Human approval |
| P3 | FFA freight rate hedging (72h) | $380,000 | MEDIUM | Human approval |
| P4 | Alternate supplier qualification (2 wks) | $200,000 | LOW | Human approval |
| **Total** | | **$1,850,000** | | |

**Do-nothing cost:** $1,700,000 · **Cost avoidance rate: 109%**

### Unit economics

| Metric | Value |
|---|---|
| Enterprise licence (avg) | $100,000 / yr |
| Avg client savings / yr | $3,300,000 (2 events) |
| Client ROI | **33×** |
| Gross margin (SaaS) | ~80% |
| 10-client ARR target | $1,000,000 |

---

## 🚢 Deployment

### Primary — GitHub Pages (live now)
```
https://benny-tang.github.io/aegis-pro-v1
```
Static HTML — zero server cost, zero downtime, works with or without API key.

### Secondary — Google AI Studio
Upload `app.py` + `requirements.txt` + `index.html` to AI Studio.
Set `GEMINI_API_KEY` environment variable. Click Deploy.

### Tertiary — Google Colab + ngrok
Run `Aegis_Pro_v1_LIVE_UI.ipynb` Cell 4 with your ngrok authtoken.
Generates a temporary public URL valid for the Colab session duration.

---

## 📁 Project Structure

```
aegis-pro-v1/
├── index.html                              # Live investor UI (GitHub Pages)
├── app.py                                  # Flask backend (AI Studio / local)
├── requirements.txt                        # Python dependencies
├── Aegis_Pro_v1_LIVE_UI.ipynb             # Full Colab notebook (4 cells)
├── Aegis_Pro_v1_TechEx_SanJose_2026.ipynb # Original pipeline notebook
├── DEPLOYMENT.md                           # Deployment guide
├── README.md                               # This file
└── assets/
    ├── AegisPro_v1_PitchDeck.pptx         # 12-slide investor pitch deck
    └── AegisPro_v1_VideoScript.md         # 3-minute video script
```

---

## 🗺️ Roadmap

| Milestone | Timeline | Deliverable |
|---|---|---|
| ✅ TechEx San Jose hackathon | May 2026 | v1 live · pitch deck · GitHub Pages |
| 🔄 Veea TerraFabric pilot | Q3 2026 | Edge deployment reference customer |
| 🔜 First beta client | Q3–Q4 2026 | $50K ARR · MVP feature freeze |
| 🔜 Pre-seed round | Q1 2027 | $250K · team + sales motion |
| 🔜 10 enterprise clients | Q4 2027 | $1M ARR · Series A ready |

---

## 🤝 Contributing

```bash
git clone https://github.com/Benny-Tang/aegis-pro-v1.git
cd aegis-pro-v1
git checkout -b feature/your-feature-name
# make changes
git commit -m "feat: your feature description"
git push origin feature/your-feature-name
# open a Pull Request
```

---

## 👥 Team

Built at **TechEx San Jose 2026** — LabLab.ai Intelligent Enterprise Solutions Hackathon.

| Role | Responsibility |
|---|---|
| ML Engineer | ARIMA + XGBoost forecaster · agent pipeline |
| AI Engineer | Gemini 3 Flash integration · multi-turn reasoning |
| Backend Engineer | Veea edge deployment · ERP integrations |
| Business Lead | Investor case · pitch deck · go-to-market |

---

## 📄 License

```
MIT License

Copyright (c) 2026 Aegis Pro Team

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

<div align="center">

**🛡️ Aegis Pro v1**
*Signal to action in 60 seconds*

**[LIVE DEMO](https://benny-tang.github.io/aegis-pro-v1)** · [TechEx San Jose 2026](https://lablab.ai/) · Powered by [Gemini 3 Flash](https://ai.google.dev/) + [Veea](https://www.veea.com/)

</div>
