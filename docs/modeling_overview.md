# Modeling overview

## 1) Forecasting
Goal: forecast near-term demand for planning.

Default proposals (confirm if needed):
- Targets: daily revenue and daily units
- Horizon: 14 days
- Evaluation: rolling time-series backtest

Baselines:
- seasonal naive (same weekday last week)
- 7-day moving average

Model:
- LightGBM using lag/rolling features from `features.daily_sales`

Output:
- write results to `mart.forecast_results`

## 2) Expected price + anomaly detection
Goal: estimate expected sale price and flag unusual deals.

Model:
- regression predicting `Sale Price`

Anomaly score:
- absolute residual: `|actual - expected|`

Default proposal (confirm if needed):
- flag top 1% by absolute residual

Output:
- write results to `mart.anomalies`

## Notes
- No PII in features or outputs.
- Keep models simple; correct evaluation matters more than heavy tuning.
