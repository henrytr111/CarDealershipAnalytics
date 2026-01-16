# Data dictionary

One row represents one sale transaction.

| Column | Type (clean) | Description | Example | Constraints | Used in |
|---|---|---|---|---|---|
| Date | date | Sale date | 2024-01-15 | not null | KPIs, features |
| Salesperson | text | Salesperson name | Alex Kim | not null | KPIs, features |
| Customer Name | text | Customer name (PII) | (redacted) | never in outputs | none |
| Car Make | text | Make | Toyota | not null | KPIs, features |
| Car Model | text | Model | Corolla | not null | KPIs, features |
| Car Year | int | Model year | 2018 | 2010–2022 | KPIs, features |
| Sale Price | numeric | Sale price (USD) | 22000 | > 0 | KPIs, target |
| Commission Rate | numeric | Commission rate | 0.10 | 0.05–0.15 | checks |
| Commission Earned | numeric | Commission amount | 2200 | ~ price×rate | checks |

## Derived fields (clean layer)
- `commission_expected = sale_price * commission_rate`
- `commission_error = commission_earned - commission_expected`
- Optional: `customer_id` (hashed) if needed for internal grouping (never display raw name)

## Defaults to confirm
- Commission reconciliation tolerance (default proposal):
  `abs(commission_error) <= max(1.0, 0.01 * commission_expected)`
- Duplicate definition (default proposal): exact duplicate rows across all columns
