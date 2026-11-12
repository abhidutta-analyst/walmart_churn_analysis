# Walmart Sales: Exploratory Data Analysis, RFM Segmentation & Customer Churn Analysis

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-orange.svg)](https://pandas.pydata.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626.svg)](https://jupyter.org/)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard%20Template-F2C811.svg)](https://powerbi.microsoft.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 📌 Executive Summary

This repository contains an end-to-end retail data analytics project focusing on **Walmart sales transactional data, RFM customer segmentation, cohort retention tracking, and customer churn analysis**. 

The project bridges raw transactional data extraction and business intelligence by combining a comprehensive Jupyter notebook (`walmart_sales_analysis.ipynb`) with an interactive Power BI dashboard template (`walmart_sales.pbit.zip`) and custom design theme (`Theme.json`). It answers critical business questions regarding revenue concentration, customer lifetime value, purchasing seasonality, and behavioral differences between active and churned customers.

---

## 🔍 Key Business Questions Addressed

The analysis inside `walmart_sales_analysis.ipynb` methodically addresses **9 core business and analytical questions**:

1. **Product Categories & Revenue Concentration**: Which product categories and stock items generate the highest revenue, and how concentrated is revenue distribution? *(Bar chart + Pareto analysis)*
2. **Revenue Over Time & Seasonality**: How does revenue fluctuate over time, and what monthly or seasonal purchasing patterns exist? *(Time-series line chart + Heatmap)*
3. **Customer Revenue Concentration**: Which customer segments generate the highest revenue, and what percentage of total revenue originates from the top 20% of customers? *(Pareto analysis / 80/20 rule)*
4. **Frequency vs. Spending Behavior**: Is there a measurable correlation between customer purchase frequency and total monetary spending? *(Scatter plot + OLS Regression line)*
5. **RFM Score Distribution**: How are customers distributed across purchasing behaviors based on Recency, Frequency, and Monetary (RFM) scoring? *(RFM segmentation matrix)*
6. **Customer Cohort Retention**: How does customer retention evolve over time, and what percentage of customers return in subsequent months after their first transaction? *(Cohort retention heatmap)*
7. **Segment Revenue & Inactivity**: Which customer segments contribute the most revenue, and which segments exhibit the highest inactivity and churn risk rates? *(Grouped bar chart & segment breakdown)*
8. **Active vs. Inactive Behavioral Comparison**: Do churned/inactive customers demonstrate statistically significant differences in purchasing frequency, average order value, or basket size compared to active customers? *(Box plots & statistical summaries)*
9. **Ecommerce Dashboard Data Export**: Transformation, enrichment, and automated export of production-ready analytics data (`EcommerceDashboardData.csv`) for BI consumption.

---

## 📂 Repository Structure

```text
Walmart_dashboard/
├── EcommerceDashboardData.csv         # Processed dataset containing RFM scores, cohorts, and churn metrics
├── README.md                          # Comprehensive project documentation
├── Theme.json                         # Custom Power BI JSON color theme and styling configuration
├── walmart_sales.csv                  # Raw Walmart transactional sales dataset
├── walmart_sales.pbit.zip             # Power BI Template for interactive dashboard reporting
└── walmart_sales_analysis.ipynb       # Main Jupyter notebook executing EDA, RFM, and Churn analysis
```

---

## 📊 Dataset Architecture & Data Dictionary

### 1. Raw Dataset (`walmart_sales.csv`)
- **`id`**: Unique transaction record identifier.
- **`invoice`**: Invoice number associated with the transaction.
- **`stock_code`**: Product stock code.
- **`description`**: Product description.
- **`quantity`**: Quantity of items purchased in the transaction.
- **`invoice_date`**: Timestamp of the transaction.
- **`price`**: Unit price of the product.
- **`customer_id`**: Unique identifier for the customer.
- **`country`**: Geographic location of the transaction.
- **`inserted_at`**: Database insertion timestamp.
- **`category`**: Product merchandise category.

### 2. Processed Dashboard Dataset (`EcommerceDashboardData.csv`)
In addition to the raw attributes, the processed dataset includes engineered metrics:
- **`total_sales` / `revenue`**: Calculated as `quantity * price`.
- **`year_month` / `month` / `year`**: Temporal breakdown dimensions.
- **`cohort_month`**: Customer's first purchase month for cohort analysis.
- **`recency`**: Days since the customer's last purchase relative to analysis cutoff.
- **`R_Score` / `F_Score` / `M_Score`**: Quantile-based RFM ratings (1 to 5).
- **`segment`**: Actionable customer segment (e.g., *Champions*, *Loyal Customers*, *At Risk*, *Churned*).
- **`is_churned`**: Binary indicator flagging inactive/churned customers based on recency thresholds.

---

## 🛠️ Methodology & Analytical Pipeline

1. **Data Preprocessing & Cleaning**:
   - Handled missing values, formatted datetime fields, and filtered out anomalies (e.g., negative quantities/returns or invalid prices).
2. **Exploratory Data Analysis (EDA)**:
   - Evaluated sales trends across time, top-performing product categories, and geographical distribution.
3. **RFM Segmentation**:
   - Calculated Recency, Frequency, and Monetary values for every customer.
   - Assigned quintile scores (1–5) and categorized customers into behavioral personas to guide targeted marketing and retention campaigns.
4. **Customer Cohort Retention Analysis**:
   - Grouped customers by their acquisition month (`cohort_month`) and tracked repeat purchase rates over a rolling timeline.
5. **Churn & Behavioral Analysis**:
   - Defined churn criteria based on inactivity thresholds.
   - Compared active vs. inactive customer metrics using descriptive statistics and visual box plots.
6. **Dashboard Integration**:
   - Exported clean dimensional tables (`EcommerceDashboardData.csv`) paired with a custom Power BI theme (`Theme.json`) and template (`walmart_sales.pbit.zip`).

---

## 🚀 Getting Started & Installation

### Prerequisites
- Python 3.8+
- Jupyter Notebook or JupyterLab
- Pandas, NumPy, Matplotlib, Seaborn
- Power BI Desktop (optional, for viewing the `.pbit` template)

### Quick Start
1. **Clone the repository**:
   ```bash
   git clone https://github.com/abhidutta-analyst/walmart_churn_analysis.git
   cd Walmart_dashboard
   ```

2. **Install required Python packages**:
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

3. **Run the Analysis Notebook**:
   ```bash
   jupyter notebook walmart_sales_analysis.ipynb
   ```

4. **Open the Power BI Dashboard**:
   - Extract `walmart_sales.pbit.zip` (or open directly in Power BI Desktop).
   - Apply `Theme.json` for custom styling and connect to `EcommerceDashboardData.csv`.

---

## 💡 Key Insights & Strategic Recommendations

- **Revenue Concentration**: A minority of customers (top 20%) generate a disproportionate share of total revenue, emphasizing the critical importance of retention programs for high-value segments (*Champions* and *Loyal Customers*).
- **Churn Risk Identification**: Inactive customers show a distinct drop in purchase frequency prior to lapsing. Implementing automated re-engagement triggers when recency exceeds specific thresholds can recover at-risk accounts.
- **Product Mix Optimization**: Core top-performing categories drive the bulk of transaction volume; cross-selling secondary categories to high-frequency shoppers can increase Average Order Value (AOV).

---

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
