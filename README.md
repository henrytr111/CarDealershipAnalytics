# Dealership Revenue Intelligence Platform

Production-style analytics + forecasting + pricing anomaly detection built on dealership transaction data.

## Problem
Dealership leadership needs:
- reliable revenue/unit forecasts,
- pricing discipline and anomaly detection,
- commission reconciliation,
- fair performance benchmarking across salespeople.

## Solution (what this repo will deliver)
- Analytics-ready tables (documented star schema + data quality checks)
- KPI dashboard: overview, product mix, sales team, anomalies
- ML models:
  - time-series forecasting for units/revenue
  - expected sale price estimation + anomaly flags
- API specification for forecast and expected-price inference
- Model cards, architecture diagram, and operational runbook

## Repository structure
- `docs/` — project specs, architecture, runbook, templates
- `data/` — local-only data storage (raw data not committed)
- `pipelines/` — ETL / feature pipeline (to be implemented)
- `models/` — training and inference code (to be implemented)
- `app/` — dashboard + API (to be implemented)
- `reports/` — final report and figures
- `tests/` — data/model tests (to be implemented)

## Data & privacy
- The source dataset includes **Customer Name** (PII).
- All public outputs remove or anonymize PII.
- Raw data must not be committed. See `data/README.md`.

## Roadmap
Use GitHub Issues/Milestones to track phases and deliverables.
