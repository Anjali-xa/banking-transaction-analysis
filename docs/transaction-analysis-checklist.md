# Banking Transaction Data Validation & Analysis Checklist

Apply this checklist before analysing or sharing transaction data. Public portfolio work should use appropriately licensed public or synthetic data only.

## 1. Source and privacy
- [ ] Record the dataset source, version, download date, licence, and coverage period.
- [ ] Confirm that the data is public or synthetic and permitted for portfolio use.
- [ ] Never commit real customer names, account numbers, card numbers, addresses, credentials, or other personal financial data.
- [ ] Remove or mask identifiers where appropriate; explain the treatment.

## 2. Data validation
- [ ] Parse transaction timestamps with the documented timezone.
- [ ] Confirm amount, currency, debit/credit direction, and transaction status.
- [ ] Check duplicate transaction IDs and repeated records.
- [ ] Inspect missing merchant, channel, category, and location values.
- [ ] Validate that amounts follow the dataset's sign convention.
- [ ] Separate pending, reversed, declined, and completed transactions.
- [ ] Reconcile row counts and totals before and after cleaning.

## 3. Define metrics before calculating
| KPI | Suggested definition | Document |
|---|---|---|
| Transaction volume | Count of eligible transactions | Statuses included |
| Total transaction value | Sum of eligible amounts | Currency and sign convention |
| Average transaction value | Total value / eligible transaction count | Treatment of reversals |
| Channel share | Transactions in a channel / all eligible transactions | Channel mapping |
| Category share | Category value or count / total | Category mapping |
| Exception rate | Flagged records / eligible records | Rule used to flag |

## 4. Responsible anomaly review
- [ ] Treat unusual patterns as review flags, not proof of fraud.
- [ ] Document thresholds and rule logic.
- [ ] Check whether time zones, duplicate imports, or reversals explain outliers.
- [ ] Avoid exposing individual-level records in charts or screenshots.
- [ ] Report false-positive limitations where applicable.

## 5. Reproducible workflow
- [ ] Keep raw data unchanged and store cleaned data separately when licensing allows.
- [ ] Use SQL for documented aggregations and Python for validation/visualisation.
- [ ] Keep transformations and assumptions in version control.
- [ ] Label chart units, currencies, periods, and sample sizes.
- [ ] Summarise findings without making unsupported causal or fraud claims.
