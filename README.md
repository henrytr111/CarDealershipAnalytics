# Car Dealership Analytics (SQL + Dashboard + ML)

End-to-end analytics project using car dealership transactions:
- a Postgres-backed SQL data model and KPI views,
- a Streamlit dashboard for business KPIs,
- two lightweight ML outputs: sales/revenue forecasting and pricing anomaly detection.

This repo is designed to be simple to run and easy to review.

## Problem
Dealership leaders want to:
- track revenue and unit trends,
- understand product mix and salesperson performance,
- forecast near-term revenue/units for planning,
- flag suspiciously under/over-priced deals for review,
- sanity-check commission calculations.

## Data (summary)
~2.5M rows, one row per sale:
`Date`, `Salesperson`, `Customer Name` (PII), `Car Make`, `Car Model`, `Car Year`, `Sale Price`, `Commission Rate`, `Commission Earned`.

Customer Name is treated as PII and is not shown in outputs.

## Quickstart (Day 1)
1) Create environment variables:
```bash
cp .env.example .env
```

2) Start Postgres + dashboard:
```bash
docker compose up --build
```

Open:
- Dashboard: http://localhost:8501
- (Optional) API: http://localhost:8000/docs

## Next steps (Day 2)
- Place the raw file locally at `data/raw/car_sales.csv` (not committed)
- Load raw data into Postgres (`raw.sales`)
- Run the SQL pipeline to build `clean.*`, `mart.*`, and `features.*`

## Repo structure
- `docs/` — short documentation
- `data/` — local-only data instructions (raw data not committed)
- `pipelines/sql/` — SQL scripts building `raw → clean → mart → features`
- `app/dashboard/` — Streamlit dashboard
- `app/api/` — optional FastAPI service
- `models/` — model training scripts (forecast + expected price)
- `reports/` — screenshots and final writeup
- `tests/` — minimal data/model tests

## Privacy
- `Customer Name` is PII.
- Do not display it in dashboards, reports, logs, or model artifacts.
- Raw data must not be committed. See `data/README.md`.
