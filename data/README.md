# Data directory

This project uses a dataset that includes **Customer Name**, which is treated as **PII**.

## Rules
- Do **not** commit raw data to GitHub.
- Store local files under:
  - `data/raw/` (original downloads)
  - `data/interim/` (cleaning outputs)
  - `data/processed/` (analytics-ready tables / features)
- Commit only:
  - documentation about data
  - small **anonymized** samples (optional) in `data/sample/`

If you need a sample for tests or screenshots, create `data/sample/sample_anonymized.csv`
with a small number of rows and **no customer names**.
