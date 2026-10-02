# /data

## Status: raw data excluded from this repository — resolved, not pending

The dataset was originally sourced from Kaggle. After a thorough search, the exact listing (title, URL, license) could not be re-located. Rather than guess at attribution or leave this open indefinitely, the decision here is simple: **the raw dataset is not redistributed in this repository.**

This is a normal, defensible outcome — not a workaround. Plenty of published analyses work from data they don't have the right to redistribute; the standard practice is exactly this: publish the analysis, the method, and the findings, and leave the raw file out.

## What this means practically

- **`workbook/`** should contain a copy of the workbook with the `Raw_Data` sheet's rows removed (keep the header row and column structure so the schema is still visible — just clear the 3,000 data rows). Everything else — `Cleaned_Data`'s structure, `EDA`, `Regression_v2`, `Dashboard`, `Executive_Summary` — can stay exactly as is, since none of those redistribute the original rows verbatim beyond aggregated/derived figures.
- If you'd rather not edit the workbook at all, keep the full working file private (on your own machine, not in the repo) and only push the four items above. The documentation, screenshots, and dashboard already communicate everything a reviewer needs to evaluate the work.
- **Do not state a specific Kaggle URL, dataset title, or license you can't verify.** The line below is the accurate, complete statement — nothing more is owed here.

## Attribution statement to use (final, as-is)

> This project uses a dataset originally obtained from Kaggle. The specific dataset listing could not be re-located at the time of publication, and the raw data is therefore not redistributed in this repository. All figures, calculations, and findings presented are derived from that dataset and are independently reproducible from the methodology documented in `documentation/`.

Use that sentence as-is in the root README and on the portfolio site. It is honest, it does not claim anything unverifiable, and it closes the question rather than leaving it open.
