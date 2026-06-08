# Canadian GST/HST Net Tax Analysis (2019–2023) — Alteryx Workflow

An Alteryx data-prep and validation workflow built on real CRA GST/HST statistics — blending five years of data across all provinces and territories into one verified dataset.

## The Question
How much GST/HST do Canadian businesses collect, how much do they reclaim as input credits, what do they remit as net tax — and does the data reconcile?

## Data Sources (real, open)
CRA GST/HST Statistics 2025 Edition (2019–2023), Open Government Licence – Canada:
- Table 2 — GST/HST collected by jurisdiction
- Table 3 — Input tax credits by jurisdiction
- Table 4 — Net tax by jurisdiction

Dataset: https://open.canada.ca/data/en/dataset/16291938-ae5d-40db-90e3-8b6c09a86ad9

## Workflow Canvas
![Alteryx Workflow Canvas](canvas.png)

## What the Workflow Does
1. **Ingest** — loads three CRA source tables
2. **Reshape** — unpivots year columns (2019–2023) into tidy Jurisdiction | Year | Value format
3. **Blend** — joins the three metrics on Jurisdiction + Year into one dataset (70 records)
4. **Calculate** — ITC Ratio and Net Tax Margin per province, per year
5. **Validate** — reconciliation check confirms Net Tax = Collected − ITCs (zero exceptions across all 70 records)
6. **Output** — exports the verified analytical dataset to Excel

## Tools Used
Input Data · Filter · Transpose · Select · Join · Formula · Sort · Auto Field · Browse · Output Data

## Key Findings
- 2023: businesses collected ~$387.6B in GST/HST, reclaimed ~$313.5B as input credits, remitted ~$74.1B net
- The 2020 COVID dip is visible in collections; the Northwest Territories posted negative net tax that year
- Input-tax-credit ratios vary by province with economic structure

## Files
- `GST_HST_Analysis.yxmd` — the Alteryx workflow
- `GST_HST_Analysis.xlsx` — the output dataset
- `canvas.png` — the annotated workflow canvas

## Notes
Built on aggregate public data to demonstrate a repeatable tax-analytics data-prep and validation pipeline.
