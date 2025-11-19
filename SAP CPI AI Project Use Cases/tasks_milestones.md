# Tasks & Milestones

## Project 1 – Error Classification AI (Week 1–2)
- Day 1–2: Connect to MessageProcessingLog OData API, pull last 7 days failures
- Day 3–4: Build REST call to /classifyError (mock). Store results in Data Store
- Day 5: Daily summary email (top 5 error categories)
- Week 2: Optional auto-retry for transient issues, finalize docs

## Project 2 – Data Enrichment AI (Week 3–4)
- Day 1–2: REST sender → JSON validation → merge enrichment
- Day 3–4: Invoke /enrichCustomer mock; handle timeouts/fallbacks
- Day 5: Deliver to Snowflake REST/JDBC mock; add audit logs
- Week 2: Feedback loop table + reprocessing

## Project 3 – Predictive Monitoring (Week 5–6)
- Day 1–2: Collect metrics via CPI API; persist to store
- Day 3–4: Invoke /predictFailures mock; compute risk levels
- Day 5: Email/Teams alert; SAC-ready CSV export
- Week 2: Hardening, docs, dashboard stub
