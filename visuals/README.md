# /visuals

**Action needed before publishing:** this folder is currently empty. Export and add:

1. A full screenshot of the `Dashboard` sheet (all four KPIs and five charts visible).
2. A screenshot of the `Regression_v2` regression summary output (coefficients, R², ANOVA table).
3. At least one of the five residual diagnostic plots from `Regression_v2` — this is the visual evidence of the validation gate, and worth showing precisely because it demonstrates a check most portfolio projects skip.
4. Optionally, one EDA PivotChart (e.g., average yield by farm size band).

## Before adding a screenshot, confirm

- It reflects the **current, corrected** workbook — not an earlier version. (Two screenshots shared during this project's review process showed chart-title/data mismatches that were later fixed; do not reuse those.)
- Every chart title visible in the screenshot matches what the chart actually plots. This was specifically verified against the underlying data bindings for the current dashboard — a new screenshot should still be visually spot-checked against `workbook/README.md`'s sheet descriptions before upload.
- File names are descriptive, e.g. `dashboard-overview.png`, `regression-output.png`, `residual-diagnostic-farm-size.png` — not `Screenshot 2026-09-18.png`.

## Suggested caption text (for the portfolio site or repo, once images are added)

- Dashboard: "Interactive summary of production drivers across 3,000 farms, built entirely in native Excel — KPIs, grouped comparisons, and a coefficient/impact chart."
- Residual plot: "Validation check confirming the regression model shows no systematic bias against any predictor — the step that caught and prevented a false finding earlier in this project (see root README)."
