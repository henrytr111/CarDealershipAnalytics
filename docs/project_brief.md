# Project brief

## Goal
Create a small internal analytics tool for a car dealership using transaction data:
- reliable KPI reporting (SQL),
- a simple dashboard for exploration,
- two ML outputs: (1) near-term forecast and (2) pricing anomaly flags.

## Users
- General manager: trend monitoring + forecast outlook
- Sales manager: product mix and salesperson performance + anomaly review
- Finance: commission sanity-check

## Deliverables
- Postgres SQL pipeline: `raw → clean → mart → features`
- Streamlit dashboard (executive, mix, salesperson, anomalies)
- Forecast results (baseline vs model)
- Expected price model + anomaly table
- Short final report in `reports/`

## Out of scope
- Inventory optimization
- Marketing attribution
- Customer segmentation

## Success criteria
- Dashboard KPIs are consistent and reproducible.
- Forecast evaluation is time-aware and compared to baselines.
- Anomalies are reviewable and explained at a high level.
- No PII is exposed (Customer Name never appears in outputs).
