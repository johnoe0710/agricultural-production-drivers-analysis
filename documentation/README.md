# /documentation

Four documents, each independently audited against the actual workbook (not written from memory of what the analysis should show). Read them in this order if you're new to the project:

1. **`Deliverable1_Executive_Briefing.docx`** — Start here. Business-facing summary: objective, headline finding, what the data shows, business implications, the correction made mid-project, and limitations. No Excel knowledge required to read this one.

2. **`Deliverable2_System_Architecture.docx`** — For a technical reviewer. Full workbook architecture, the exact regression specification, the validation-gate methodology, and the complete root-cause record of the ratio-based defect that was found and removed.

3. **`Deliverable3_Operating_Maintenance_Manual.docx`** — For anyone extending this project. Step-by-step: adding new data, refreshing PivotTables, re-running the regression, and the mandatory validation check that must pass before trusting any refit.

4. **`Deliverable4_Data_Dictionary.docx`** — Field-by-field reference. Every variable in every sheet, each explicitly tagged **Confirmed** or **Assumed** — including the two open items (the unit of `crop_yield`, and the dataset's exact source/license) that are not resolved and are stated as such rather than glossed over.

## Audit trail

These documents went through two rounds of independent verification before publication:

- **Round 1** checked the documentation against the actual workbook formulas, chart bindings, and regression output, catching several chart-title mismatches and unit-range errors.
- **Round 2** specifically checked for claims that could make the project look more sophisticated than the work performed — catching an instance of descriptive analysis being described as "predictive," and a finding overstated as a clean trend where the underlying grouped data was actually noisy.

Both rounds resulted in corrections that are reflected in the current versions of these four files. This audit trail is not itself included as a fifth document, but it is the reason the wording in these four documents is careful rather than promotional.
