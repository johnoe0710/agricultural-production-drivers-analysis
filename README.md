# Agricultural Production Drivers Analysis

**Author:** John O. Ezekiel
**Tools:** Microsoft Excel (Tables, PivotTables/PivotCharts, Data Analysis ToolPak)
**Dataset:** 3,000 farm-level observations
**Status:** Corrected and independently audited — see [Correction & Audit History](#correction--audit-history) below

---

## Objective

This project investigates which environmental and operational factors — farm size, fertilizer application, rainfall, soil quality, and sunlight exposure — are most strongly **associated** with total crop output across 3,000 farm holdings, using descriptive and exploratory statistical methods in Excel.

This is an **explanatory/exploratory analysis**, not a validated predictive model: no train/test split, holdout sample, or cross-validation was performed. See [Limitations](#limitations).

## Data

- **Records:** 3,000 rows, 6 base variables (`rainfall_mm`, `soil_quality_index`, `farm_size_hectares`, `sunlight_hours`, `fertilizer_kg`, `crop_yield`).
- **Source:** originally obtained from Kaggle. The specific dataset listing could not be re-located at the time of publication, and the raw data is therefore **not redistributed in this repository** — see [`data/README.md`](data/README.md). All figures, calculations, and findings presented are derived from that dataset and are independently reproducible from the methodology documented here.
- **Units:** Documented in full in [`documentation/Deliverable4_Data_Dictionary.docx`](documentation/Deliverable4_Data_Dictionary.docx). Two units (`crop_yield`'s measure, and the measurement period for `rainfall_mm`/`sunlight_hours`) are **assumed, not confirmed** — this is stated explicitly rather than glossed over.
- **Integrity:** Verified duplicate-free and null-free across all 3,000 records; the working copy (`Cleaned_Data`) was independently diffed cell-by-cell against the raw source and confirmed identical on all base columns.

## Method

1. Data cleaning and validation (Excel Tables).
2. Feature engineering: one categorical field (`farm_size_band`) for grouping — no ratio-based fields are used in the final model (see [Correction History](#correction--audit-history)).
3. Exploratory data analysis via native Excel PivotTables/PivotCharts.
4. Statistical modeling: multiple linear regression (Ordinary Least Squares) via the Data Analysis ToolPak, with `crop_yield` as the dependent variable.
5. **Mandatory validation gate:** residuals checked against every predictor and confirmed patternless (correlations on the order of 10⁻¹³ to 10⁻¹⁵) before any finding was reported.
6. Dashboard and executive reporting built only after the validation gate passed.

## Tools

Microsoft Excel only — native Tables, PivotTables/PivotCharts, and the Data Analysis ToolPak add-in. **No Power Query, Power BI, or DAX is used in this project.**

## Findings (summary)

- Farm size is the strongest factor associated with total output (r = 0.989).
- Soil quality, fertilizer, rainfall, and sunlight are all positively associated with output, to a modest degree.
- The five-factor model explains 99.9996% of output variance in this dataset — an unusually clean result, which the project's own limitations section flags as evidence the dataset is likely synthetic rather than field-collected.

Full findings, with all figures independently reproduced and verified: [`documentation/Deliverable1_Executive_Briefing.docx`](documentation/Deliverable1_Executive_Briefing.docx).

## Limitations

- **Association, not causation.** This is observational data; no factor was experimentally varied. Findings should be read as "associated with," never "causes."
- **Explanatory, not predictive.** No out-of-sample validation was performed. R² measures in-sample fit only.
- **Unconfirmed units** for `crop_yield` and the measurement period of `rainfall_mm`/`sunlight_hours` (see Data section above).
- **Raw data is not redistributed in this repository** — its exact original source could not be re-located; see `data/README.md`.

## Reproduction

Full step-by-step instructions — adding new data, refreshing PivotTables, re-running the regression, and re-running the mandatory validation gate — are in [`documentation/Deliverable3_Operating_Maintenance_Manual.docx`](documentation/Deliverable3_Operating_Maintenance_Manual.docx). No installation beyond Microsoft Excel with the Data Analysis ToolPak add-in (built into Excel, enabled via Options) is required.

## Correction & Audit History

An earlier version of this analysis computed an efficiency ratio (`crop_yield ÷ farm_size`) and concluded that larger farms show declining efficiency ("diseconomies of scale"). This was independently audited, found to be a **mathematical artifact** of dividing a variable by itself's own scaling factor — not a real relationship — and fully corrected. The full root-cause analysis is documented in [`documentation/Deliverable2_System_Architecture.docx`](documentation/Deliverable2_System_Architecture.docx), Section 6.

This history is included deliberately: catching and correcting this kind of error is part of the demonstrated work, not something to hide.

## Repository Structure

```
├── workbook/         → the Excel workbook (analysis, model, dashboard)
├── documentation/    → the four deliverable documents (briefing, architecture, manual, data dictionary)
├── visuals/          → exported screenshots of the dashboard and key charts
└── data/             → data provenance notes (see note on redistribution status)
```

Each folder has its own `README.md` with folder-specific detail.
