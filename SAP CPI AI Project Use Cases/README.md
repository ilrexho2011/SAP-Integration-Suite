# CPI AI Project Pack (v3 – Fully Free and Open Source)
Prepared: 2025-11-13

This version contains all three CPI × AI use cases with a 100% free and open‑source stack.
Everything here can be deployed on free services like GitHub Codespaces, Render, or Replit.

---

## 🚀 Included Use Cases

### 1️⃣ Intelligent Error Classification & Auto‑Resolution
Automatically classify failed CPI messages and suggest corrective actions.
- Input: errorText
- Output: errorCategory, confidence, recommendedAction
- Example: 401 Unauthorized → Authentication issue

### 2️⃣ AI‑Powered Data Enrichment
Infer missing or inconsistent data dynamically during integrations.
- Input: Incomplete master data (e.g., customer payload)
- Output: Enriched, standardized data

### 3️⃣ Predictive Integration Monitoring
Forecast failures or latency spikes before they occur.
- Input: CPI metrics (message count, latency, errors)
- Output: Risk level, anomaly score

---

## 🧠 AI Layer (Free)

| Component | Purpose | Tool |
|------------|----------|------|
| **FastAPI** | REST API service layer | MIT |
| **scikit‑learn / LightGBM / Prophet** | ML model libraries | Open source |
| **Ollama + Mistral 7B** | Local LLM for enrichment | Free |
| **BentoML (optional)** | Model packaging | Apache 2.0 |
| **Hosting** | Run on Codespaces, Render, or Replit | Free tiers |

Endpoints:
- `/classifyError` – text classification
- `/enrichCustomer` – data enrichment
- `/predictFailures` – anomaly prediction

---

## 🗄️ Data / Feature Layer (Free)

| Component | Purpose | Tool |
|------------|----------|------|
| **PostgreSQL** | Store logs and metrics | Free |
| **DuckDB** | Lightweight analytics | Free |
| **Feast** | Feature store | Apache 2.0 |
| **Grafana OSS** | Dashboards and alerts | Free |
| **Airflow / Cron** | Scheduling | Free |

Example architecture:
```
[CPI] → [FastAPI AI Layer] → [PostgreSQL/DuckDB]
                                ↓
                             [Grafana]
```

---

## 📂 Structure
- `project1_error_classification/`
- `project2_data_enrichment/`
- `project3_predictive_monitoring/`
- `ai_data_layers.md`
- `evaluation_checklist.md`
- `tasks_milestones.md`
- `postman_collection.json`

---

## ⚙️ Deployment (Free Setup)
1. Fork to GitHub → Open in Codespaces.
2. Run `uvicorn ai_error_classifier:app --host 0.0.0.0 --port 8000`.
3. Expose Port 8000 → Make Public.
4. Use that URL in CPI HTTP Receiver adapter.
5. Test live classification via HTTPS iFlow.

---

## 🌍 License
All tools are MIT / Apache / BSD / AGPLv3.
No proprietary services or paid APIs.

---
