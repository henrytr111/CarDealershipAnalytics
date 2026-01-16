# Data handling policy

## Local-only raw data
Place the raw dataset locally at:
- `data/raw/car_sales.csv`

Raw data is not committed to git.

## PII rule
`Customer Name` is PII and must never appear in:
- dashboard tables/filters
- model outputs/explanations
- logs
- screenshots/videos
- committed sample files

If a customer identifier is required, use a one-way hashed `customer_id` and never expose the raw name.

## Optional sample data
You may commit a tiny anonymized sample under `data/sample/` only if:
- customer names are removed,
- any IDs are hashed,
- rare identifying values are removed,
- the sample is small (e.g., 100–500 rows).
