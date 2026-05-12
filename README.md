# ☁️ CloudLens AI — Cloud Cost Intelligence Platform

An AI-powered cloud billing analyzer that detects spending anomalies, identifies wasted resources, and gives prioritized cost-cutting recommendations — for AWS, GCP, and Azure. Upload your billing CSV export and get a full FinOps audit in seconds.

---

## 🔍 What It Does

- **Parses** AWS Cost Explorer, GCP Billing, and Azure Cost Analysis CSV exports
- **Detects** spending anomalies — services consuming a disproportionate share of the bill
- **Identifies** wasted resources — idle dev instances, oversized compute, unnecessary data transfer
- **Estimates** potential monthly and annual savings with specific dollar amounts
- **Recommends** prioritized cost-cutting actions (reserved instances, rightsizing, lifecycle policies)
- **Answers** plain-English questions about your bill using AI

---

## 🚀 Live Demo

👉 [**Try it live →**](https://yourusername.github.io/cloudlens-ai)

**Quick start:** Click "AWS Bill Sample", "GCP Bill Sample", or "Azure Bill Sample" — no upload needed.

---

## 📸 Features

| Feature | Description |
|---|---|
| 💰 Savings Estimator | Detects waste and estimates monthly + annual savings in dollars |
| 📊 Service Breakdown | Doughnut chart + table of spend by service with % of total bill |
| 🗑️ Waste Detection | Idle dev resources, oversized instances, data transfer, storage tier waste |
| ⚠️ Anomaly Detection | Flags services consuming >15% or >30% of total bill |
| 📈 Cost Timeline | Daily spend chart to spot spikes and trends |
| 💡 Recommendations | 5 prioritized FinOps actions with estimated savings % |
| 🤖 AI Analyst | Ask any question about your bill in plain English |
| ⬇️ Report Export | Download full cost report as text |

---

## 🧠 How It Works

```
Cloud Billing CSV Upload (AWS / GCP / Azure)
    ↓
Auto-detection of cost, service, date, region columns
    ↓
Spend Analysis Engine
    ├── Service aggregation (group by service, sum costs)
    ├── Anomaly detection (% share threshold: >15% warning, >30% critical)
    ├── Waste pattern matching (dev/staging, oversized, transfer, logging, storage)
    └── Timeline aggregation (daily spend by date)
    ↓
Savings Calculation (waste × reduction factor per category)
    ↓
Visualization (Chart.js — doughnut + timeline)
    ↓
AI Analyst (Claude AI) — auto-summary + natural language Q&A
```

### Waste Detection Categories

| Category | Detection Method | Avg Savings |
|---|---|---|
| Idle dev/staging resources | Region/tag pattern matching | 60% of dev cost |
| Oversized instances | Instance type regex (xlarge, 2xlarge) | 35% |
| Data transfer | Transfer/bandwidth/egress keyword match | 40% |
| Excessive logging | Log/monitor service detection | 50% |
| Unoptimized storage | Storage service + tier analysis | 45% |

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| AI Engine | Claude AI (claude-sonnet-4) via Anthropic API |
| CSV Parsing | PapaParse 5.4 (handles messy real-world exports) |
| Data Visualization | Chart.js 4.4 (doughnut + line charts) |
| Cost Analysis | Vanilla JS (aggregation, anomaly scoring, waste heuristics) |
| Frontend | HTML / CSS / JavaScript |
| Deployment | GitHub Pages |
| Cloud Providers | AWS, GCP, Azure billing format support |

---

## 📂 Project Structure

```
cloudlens-ai/
├── index.html       # Full app — billing parser, analysis engine, dashboard, AI chat
└── README.md
```

---

## ⚙️ Run Locally

```bash
git clone https://github.com/yourusername/cloudlens-ai
cd cloudlens-ai
open index.html
```

No install. No server. Works with any billing CSV export.

---

## 📊 Supported Billing Formats

| Provider | Export Source | Columns Used |
|---|---|---|
| AWS | Cost Explorer → Download CSV | Service, Region, Cost, Usage Type, Date |
| GCP | Billing → Export → CSV | Service, SKU, Region, Cost, Project |
| Azure | Cost Analysis → Download | Service Name, Resource Group, Location, Cost |
| Generic | Any billing CSV | Auto-detects cost, service, date columns |

---

## 🎯 Why I Built This

Cloud waste is a massive problem — Gartner estimates organizations waste 30-35% of their cloud spend. Tools like AWS Cost Explorer show you the data but don't tell you *what to do*. CloudLens AI acts like a FinOps analyst: it reads your bill, finds the waste, and gives you a prioritized action list with estimated savings.

This project demonstrates:
- Cloud computing architecture knowledge (AWS, GCP, Azure services)
- Anomaly detection on time-series financial data
- Data mining and pattern matching on billing records
- Applied AI for domain-specific financial analysis
- FinOps methodology (rightsizing, reserved capacity, lifecycle policies)

---

## 📋 Example Output

```
File: aws_billing_export.csv
Total Spend:      $2,847.30
Estimated Waste:  $892.40 (31% of bill)
Annual Projection: $34,167.60

Top Services:
  Amazon EC2:          $1,247.80  (43.8%)  ⚠️ CRITICAL
  Amazon RDS:          $520.00    (18.3%)  ⚠️ HIGH
  Amazon S3:           $383.30    (13.5%)
  AWS Data Transfer:   $234.50    (8.2%)
  Amazon ElastiCache:  $145.00    (5.1%)

Waste Detected:
  🖥️ Idle dev/staging resources    → save $312/mo
  📦 Oversized instances           → save $287/mo
  🔀 High data transfer costs      → save $187/mo
  🗄️ Unoptimized storage tiers     → save $106/mo

Top Action: Commit to 1-year reserved EC2 instances → saves 40-60% on compute.
```

---

## 🗺️ Roadmap

- [ ] Multi-month comparison (detect spend trends)
- [ ] Resource-level drill-down (by resource ID/tag)
- [ ] Terraform/IaC cost estimation integration
- [ ] Slack/email alert integration for anomaly spikes
- [ ] Export recommendations as PDF report
- [ ] Budget forecasting with ML trend projection

---

## 👤 Author

**Harshith Pankaja Mahendra**
CS Student @ University of New Brunswick
[LinkedIn](https://www.linkedin.com/in/harshith-mahendra-b61aa02a1)

---

> Part of an AI portfolio — see also [DataPulse AI](https://github.com/yourusername/datapulse-ai) · [PhishGuard AI](https://github.com/yourusername/phishguard-ai) · [NetWatch AI](https://github.com/yourusername/netwatch-ai)
