# Runbook

## Prerequisites
- Docker + Docker Compose
- Python 3.10 (only needed for model scripts if running outside Docker)

## Run the stack
```bash
cp .env.example .env
docker compose up --build
```

## Load raw data (Day 2+)
- Place raw CSV locally at: `data/raw/car_sales.csv`
- Run a loader script (to be added in Day 2) to load into `raw.sales`

## Build SQL tables/views (Day 2+)
- Run the SQL pipeline (to be added in Day 2)

Expected objects:
- `raw.sales`
- `clean.fact_sales` (+ dims)
- `mart.*` KPI views/tables
- `features.*` feature tables

## Common issues
- Wrong CSV delimiter/headers: confirm the raw file format matches the loader.
- Connection issues: verify `.env` values match your compose services.
