# /workbook

**Put the Excel file here** — but first, remove the raw data rows before adding it to this public repository.

## Required step before adding the workbook

Open the workbook and on the `Raw_Data` sheet, delete the 3,000 data rows (keep row 1, the headers, so the schema is still visible). This is the only change needed. Everything else in the workbook can stay exactly as it is:

- `Cleaned_Data`, `EDA`, `Regression_v2`, `Dashboard`, and `Executive_Summary` all contain your own derived work — aggregates, model coefficients, charts, and text — not a redistribution of the original raw rows. These are fine to publish as-is.
- Save this scrubbed copy under a clear name, e.g. `agricultural_production_drivers_analysis_public.xlsx`, and keep your original full working copy (with the real data) private on your own machine — do not commit it to this repo.

See `data/README.md` for why this step exists: the dataset's original Kaggle source could not be re-located, so the raw rows are excluded rather than redistributed without a confirmed license.

## What's inside the workbook

| Sheet | Purpose |
|---|---|
| `Raw_Data` | Source data schema only in the public version (rows removed — see above). |
| `Cleaned_Data` | Validated working copy, plus one engineered field (`farm_size_band`, a category label — not a ratio). |
| `EDA` | Three PivotTables (by farm size band, soil quality, fertilizer band) and a transcribed coefficient table. |
| `Regression_v2` | Ordinary Least Squares regression output: `crop_yield` modeled on farm size, rainfall, soil quality, fertilizer, and sunlight. Includes five residual diagnostic charts — the project's validation gate. |
| `Dashboard` | KPI summary and five charts, sourced from `EDA` and `Regression_v2`. |
| `Executive_Summary` | Plain-text narrative: objective, findings, interpretation, methodology, limitations. |

## Before you open it

If you're reviewing this project for the first time, read `documentation/Deliverable2_System_Architecture.docx` first — it explains why the sheet order matters (data flows one direction only) and documents the one defect that was found and removed from an earlier version.

## Maintenance

If you add new farm records to this workbook, do not skip the residual validation gate before trusting any updated finding. Full instructions: `documentation/Deliverable3_Operating_Maintenance_Manual.docx`.
