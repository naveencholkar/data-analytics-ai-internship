# Data Analytics with AI — Combined Pipeline (Masterclass 1–4)

**Program:** AICTE | IBM SkillsBuild Data Analytics with AI Internship 2026
**Company:** BharatCares
**Trainer:** Mr. Kartik Hooda

## Overview

This project runs the full data-analytics workflow taught across the four
masterclasses, on real transaction data, end to end in one pipeline:

| Part | Masterclass | What it does |
|------|-------------|---------------|
| 1 | Data Fundamentals | Cleans the raw e-commerce dataset (fixes bad dates, mixed currency formatting, negative quantities, inconsistent region/category text, duplicates, missing values) and builds a data dictionary + 5 business questions |
| 2 | AI for Data Analytics (EDA) | 5 visualizations (monthly revenue trend, category revenue, customer segments, regional revenue, top products by profit) with observations, insights, hypotheses, and recommendations |
| 3 | AI Predicts What Happens Next | Builds RFM (Recency/Frequency/Monetary) features, a leakage-safe churn label, and trains a logistic regression churn-prediction model with an evaluation report and a customer risk table |
| 4 | Business Solutions | Supermarket Sales Analysis on a separate 500-transaction retail dataset — top product, best branch, top category, top payment method, member vs. normal spend, average rating |

## Files in this submission

- `Combined_Pipeline_Masterclass_1to4.ipynb` — the notebook (recommended: open in Google Colab)
- `Combined_Pipeline_Masterclass_1to4.py` — the same pipeline as a plain Python script
- `requirements.txt` — Python package dependencies
- `README.md` — this file

## Datasets required (upload alongside the code, not included in the code file)

1. `AI_-_Data-_Make_Data_Intelligent_-_Masterclass_1_-_Practice_Dataset.xlsx` — used by Parts 1–3
2. `SUPER_MARKET_DATA.xlsx` — used by Part 4

Place both files in the same folder as the script/notebook (or upload them to
the Colab session) before running. If your filenames differ, update the
`FILENAME_MC1` and `FILENAME_MC4` variables near the top of Parts 1 and 4.

## How to run

**Option A — Google Colab (recommended)**
1. Upload `Combined_Pipeline_Masterclass_1to4.ipynb` to Colab.
2. Upload both dataset files via the Files panel.
3. Run all cells (Runtime → Run all).

**Option B — Locally**
```bash
pip install -r requirements.txt
python Combined_Pipeline_Masterclass_1to4.py
```
(Charts will pop up in separate windows / save to the current directory
depending on your matplotlib backend.)

## Key results

- **Data cleaning:** ~2000 raw rows → ~1900 clean rows after removing duplicates,
  invalid dates, and unrecoverable records.
- **EDA:** Electronics is the highest-revenue category; repeat customers make up
  the large majority of the customer base; revenue is fairly evenly spread
  across regions.
- **Churn model:** Logistic regression on Recency/Frequency/Monetary/Avg Order
  Value, trained on a historical window with the churn label taken from a
  later window (leakage-safe). Outputs accuracy/precision/recall, a confusion
  matrix, and a sorted High/Medium/Low customer risk table.
- **Supermarket analysis:** Cheese is the top-selling product, Branch C (Mumbai)
  is the best-performing branch, Beverages is the top category, UPI is the
  most-used payment method, and average rating is 3.99/5.

## Notes on methodology

- All cleaning rules (date parsing, currency stripping, quantity correction)
  are applied explicitly in code — no manual spreadsheet edits.
- The churn label is computed from a future time window, separate from the
  window used to build the RFM features, to avoid target leakage.
- Insights are phrased as associations ("may indicate", "is associated with"),
  not proven causes, per the masterclass's association-vs-causation guidance.
