# Banking Transaction Reconciliation Guide

## Reconciliation workflow
1. Confirm source files, extraction timestamps, and reporting period.
2. Validate transaction IDs and identify duplicates.
3. Reconcile opening balance + credits - debits against closing balance.
4. Separate pending, reversed, failed, and settled transactions.
5. Investigate unmatched records with documented reason codes.
6. Record tolerances and sign-off status.

## Data checks
- Preserve transaction currency and convert only with a documented rate/date.
- Validate timestamp zones and posting dates.
- Flag zero-value or negative amounts for review, not automatic deletion.
- Mask account and customer identifiers.
- Keep raw source values alongside cleaned fields.

## Anomaly review
Use transparent rules such as unusual transaction frequency, amount deviations, or repeated failed attempts. A flag is a review signal, not evidence of fraud.

## Reporting
Report matched/unmatched counts, value differences, ageing, and unresolved exceptions. Never publish personal banking data.