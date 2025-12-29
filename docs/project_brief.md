# Dealership Revenue Intelligence Platform — Project Brief

## One-liner
A production-style analytics + forecasting + pricing anomaly detection system built on dealership transaction data.

## Background
Dealership leadership needs better revenue predictability, pricing discipline, commission accuracy, and fair sales performance benchmarking.

## Users and decisions
### General Manager
- Track revenue/units trends and forecast outlook for staffing and planning.

### Sales Manager
- Identify pricing outliers and coach salespeople using fair comparisons.

### Finance / Payroll
- Validate commission payouts and detect mismatches or unusual rates.

## Goals (measurable)
- Forecast daily/weekly units and revenue with proper time-series backtesting.
- Estimate expected sale price for a given car (make/model/year + date) and flag anomalies.
- Provide salesperson benchmarking using a fairness-aware “uplift vs expected” approach.
- Deliver a dashboard for KPI monitoring + drilldowns.
- Document data quality checks, privacy handling, and model limitations.

## Non-goals
- Inventory optimization (not present in dataset).
- Marketing attribution (not present in dataset).
- Customer targeting/segmentation (PII + limited features).

## Dataset summary
- ~2.5M sales transactions over one year
- Columns: Date, Salesperson, Customer Name (PII), Car Make, Car Model, Car Year, Sale Price, Commission Rate, Commission Earned

## Deliverables
- Analytics-ready tables (documented star schema + data quality checks)
- KPI dashboard (overview, product mix, sales team, anomalies)
- Forecast model + evaluation report
- Expected-price model + anomaly flags + interpretability
- API spec (forecast + expected price + anomalies)
- Model cards + architecture diagram + operational runbook

## Success criteria
- Forecast model beats strong baselines over rolling backtests.
- Commission reconciliation rules catch mismatches with clear thresholds.
- Anomalies are actionable (review list + explanations).
- All outputs remove or anonymize PII.
