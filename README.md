# MSCS 634 — Lab 1

## Purpose
This repository demonstrates data visualization, preprocessing, and statistical analysis using Python, Pandas, Matplotlib, and scikit-learn in Jupyter Notebook.

## Files
- `MSCS_634_Lab_1.ipynb` — complete lab notebook with code, charts, and interpretations.
- `retail_sales.csv` — 120-row sample retail dataset used by the notebook.
- `Screenshots` — required screenshots of notebook outputs.

## Key insights
- Scatter and line plots help explore the relationship between sales and units sold and show daily variation.
- Product-level bar charts compare revenue across categories; histograms reveal the sales distribution.
- Missing categorical values are filled with the mode and missing numeric values with the median.
- The IQR method identifies unusual numeric observations for review.
- Sampling and dropping a less relevant column demonstrate data reduction.
- Min-Max scaling maps units sold to a 0–1 range, while sales are discretized into Low, Medium, and High categories.
- Descriptive statistics and correlation help summarize distributions and relationships, but correlation does not establish causation.

## Challenges and decisions
The sample dataset intentionally includes missing values and unusual values so the preprocessing steps can be demonstrated. The notebook removes rows flagged as IQR outliers in any selected numeric field; for real datasets, investigate flagged values before deciding whether removal is justified. A reproducible 60% sample is used for data reduction.

## How to run
1. Keep the notebook and CSV in the same directory.
2. Install dependencies if needed: `pip install pandas numpy matplotlib scikit-learn jupyter`
3. Open Jupyter Notebook and run all cells from top to bottom.
4. Enter your name in the first Markdown cell.
5. Capture the required output screenshots and save them under `screenshots/`.
