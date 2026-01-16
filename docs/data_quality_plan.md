# Data quality plan

We run checks after loading `raw.sales` and after building `clean.fact_sales`.

## Critical checks (fail the build)
1) Required columns are not null:
   - Date, Salesperson, Car Make, Car Model, Car Year, Sale Price, Commission Rate, Commission Earned
2) `Sale Price > 0`
3) `Car Year` within [2010, 2022]
4) `Commission Rate` within [0.05, 0.15]

## Reconciliation check (warn or fail based on threshold)
Commission should reconcile within tolerance:
- `commission_expected = sale_price * commission_rate`
- Default proposal:
  `abs(commission_earned - commission_expected) <= max(1.0, 0.01 * commission_expected)`

## Duplicate handling
- Identify exact duplicate rows across all columns.
- Keep the first occurrence; record the number removed.

## Reporting
Each pipeline run should produce a summary:
- total rows loaded
- rows dropped/flagged per rule
- reconciliation mismatch count
- duplicates removed count
