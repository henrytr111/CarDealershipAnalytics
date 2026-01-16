# Privacy and PII Handling

## 1) What is considered PII in this project
- Customer Name is PII.
- Any direct identifier or combination of fields that could identify an individual is treated as sensitive.

## 2) Non-negotiable rules
Customer Name must never appear in:
- dashboards (including tables and filters)
- model outputs (training data exports, predictions, explanations)
- logs
- screenshots or demo videos
- committed sample files
- reports

Default behavior: Customer Name is dropped from the clean layer and is not used in features, models, or outputs.

## 3) Allowed alternative identifiers
If customer-level grouping is required:
- Create a one-way hashed customer id derived from Customer Name.
- The hash must be stable (same input → same output) and not reversible for practical purposes.
- Do not publish any hashing salt/secret if used.

## 4) How we prevent accidental leaks
- Raw data is stored locally only under `data/raw/` and is ignored by git.
- Processed data under `data/processed/` is ignored by git.
- Only a small anonymized sample (optional) may be committed under `data/sample/`.
- No exported training datasets containing raw customer names are saved to the repo.
