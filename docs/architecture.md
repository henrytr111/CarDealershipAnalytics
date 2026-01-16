# Architecture

## Components
- Postgres (Docker): stores tables and views
- SQL pipeline: builds `raw → clean → mart → features`
- Streamlit dashboard: reads from `mart.*`
- Model scripts: read from `features.*`, write results back to `mart.*`

## Data flow
1) Raw CSV → `raw.sales`
2) Cleaning/typing → `clean.fact_sales`
3) Analytics layer → `mart.*` (KPIs)
4) Feature tables → `features.*`
5) Models produce:
   - `mart.forecast_results`
   - `mart.anomalies`
6) Dashboard reads KPIs + anomalies from `mart.*`
