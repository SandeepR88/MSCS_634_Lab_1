# Sales Data Analysis – Lab 1

## Project Overview

This project explores a sales transaction dataset using Python, pandas, and visualization libraries. The analysis covers data inspection, missing-value treatment, outlier handling, data reduction, scaling, descriptive statistics, and visual exploration of sales patterns.

The original dataset contains **120 records and 8 columns**:

- `Order_Date`
- `Region`
- `Product`
- `Units_Sold`
- `Unit_Price`
- `Discount`
- `Sales`
- `Customer_Satisfaction`

The screenshots accompanying this README document the workflow and the outputs discussed below.

## Key Insights from Visualizations and Statistical Measures

### 1. Dataset structure and descriptive statistics

The dataset contains 120 transactions across four regions and five product categories. The most frequent region is **East (38 records)**, while **Keyboard** is the most frequent product (32 records).

The numeric summaries show the following:

| Measure | Units Sold | Unit Price | Discount | Sales | Customer Satisfaction |
|---|---:|---:|---:|---:|---:|
| Mean | 7.42 | 246.00 | 0.0879 | 1,769.48 | 3.98 |
| Median | 6.00 | 90.00 | 0.10 | 465.56 | 3.95 |
| Minimum | 1 | 28.00 | 0.00 | 14.33 | 1.70 |
| Maximum | 100 | 850.00 | 0.20 | 25,000.00 | 5.00 |
| Standard deviation | 9.40 | 311.54 | 0.0622 | 3,362.02 | 0.72 |

Sales has a mean of **1,769.48**, substantially higher than its median of **465.56**. Its maximum of **25,000** and standard deviation of **3,362.02** indicate a wide spread and a strong influence from unusually large transactions. Unit price is also dispersed, with a mean of **246** and median of **90**. By contrast, customer satisfaction is more concentrated, with a mean of approximately **3.98** and a median of **3.95** on the apparent five-point scale.

### 2. Scatter plot: Units sold versus sales

The scatter plot shows that sales revenue generally varies with the number of units sold, but the relationship is not especially strong in this dataset. The correlation between `Units_Sold` and `Sales` is approximately **0.069**, indicating a very weak positive linear association. This suggests that quantity alone does not explain revenue; product price and discounts also matter. The unusually large observations should be checked before interpreting the overall pattern.

### 3. Line plot: Daily sales over time

The daily sales line plot shows substantial fluctuations, including several sharp spikes. These changes may reflect differences in the products purchased, quantities, prices, and discounts on individual dates. The data covers **January 1 through April 30, 2025**, and the plotted daily values do not establish a reliable long-term seasonal trend. More years of data and consistent daily aggregation would be needed to assess seasonality.

### 4. Bar chart: Total sales by product

The bar chart indicates that **Laptop** transactions contribute the largest total sales, with the other product categories contributing considerably less. This comparison is based on revenue, not units sold. A product can generate more revenue because of a higher selling price even if its sales volume is not the highest. Product-level decisions should therefore consider both revenue and quantity.

### 5. Histogram: Distribution of transaction sales

The sales histogram is **right-skewed**: most transactions are concentrated at relatively low sales values, while a small number of large transactions extend the distribution to the right. This pattern is consistent with the difference between the mean and median sales values. It also reinforces the need to investigate extreme transactions rather than relying on the mean alone.

### 6. Data quality: Missing values and outliers

The missing-value check identified missing entries in categorical and numeric fields. The workflow filled categorical missing values with the **mode** and numeric missing values with the **median**. The follow-up check shows **zero missing values** in the displayed columns after treatment.

The IQR-based outlier step reduced the dataset from **120 rows to 94 rows**, removing 26 records flagged in at least one selected numeric field. This is a substantial reduction (about 21.7%). Outlier removal can make summary measures less sensitive to extreme observations, but unusual transactions should be investigated before being discarded because they may represent genuine high-value sales.

### 7. Data reduction and scaling

A reproducible 60% sample of the 94-row post-outlier dataset produced **56 rows**. The reduced view also dropped `Unit_Price`, leaving seven columns. This creates a smaller dataset for demonstration, but sampling can omit rare or important transactions. The full cleaned dataset should remain the basis for final business decisions.

Min-Max scaling transformed `Units_Sold` to a range from **0 to 1**, preserving the relative ordering of observations while changing the scale. Sales values were also grouped into **Low, Medium, and High** bands using sample quantiles. These categories are relative to this dataset and should not be treated as universal business thresholds.

### 8. Correlation analysis

The correlation matrix highlights one notably stronger relationship:

| Variable pair | Correlation | Interpretation |
|---|---:|---|
| Unit Price and Sales | 0.595 | Moderate positive relationship |
| Unit Price and Discount | 0.199 | Weak positive relationship |
| Discount and Sales | 0.138 | Very weak positive relationship |
| Units Sold and Sales | 0.069 | Very weak positive relationship |
| Sales and Customer Satisfaction | -0.144 | Weak negative relationship |
| Units Sold and Customer Satisfaction | -0.024 | Negligible relationship |

The strongest observed association is between **Unit Price and Sales (r = 0.595)**. This is a moderate positive correlation, suggesting that higher-priced products tend to be associated with higher transaction revenue. The other correlations are weak or negligible. In particular, the matrix does not show a meaningful linear relationship between units sold and customer satisfaction, or between sales and customer satisfaction. Correlation describes association and does not establish causation.

## Overall Conclusion

The analysis shows that product price is more strongly associated with sales revenue than unit quantity in this sample. Laptop transactions contribute the largest product-level revenue, while transaction sales are highly right-skewed and contain unusually large values. Customer satisfaction is comparatively stable, and its correlations with the sales variables are weak.

The data-cleaning steps addressed missing values and reduced the influence of extreme observations, while sampling and scaling made the data easier to demonstrate and compare. However, the original dataset and the cleaned dataset should be retained alongside the reduced sample so that business conclusions can be checked against the full set of transactions. Future analysis could compare revenue and quantity by product and region, investigate the high-value transactions, and use a larger time range to test for seasonal patterns.

## Screenshots

The accompanying screenshot set records the notebook workflow:

1. First five rows and dataset preview
2. Scatter plot of units sold versus sales
3. Daily sales line plot
4. Total sales by product bar chart
5. Transaction sales histogram
6. Missing values before treatment
7. Missing values after treatment
8. IQR outlier handling
9. Data reduction
10. Min-Max scaling and sales bands
11. Dataset information
12. Descriptive statistics
13. Central tendency, minimum, and maximum
14. Dispersion measures
15. Correlation analysis
16. Correlation matrix visualization

## Tools and Libraries

- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook


