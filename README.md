# Walmart Sales: Exploratory Data Analysis, RFM Segmentation & Churn Analysis

## Project Overview
This repository contains a professional, semi-advanced data analysis project based on Walmart sales transactional data. The project is centered around a comprehensive Jupyter notebook (`walmart_sales_analysis.ipynb`) in the root directory that answers **8 key business and analytical questions** using exploratory data analysis, RFM segmentation, and customer cohort analysis.

---

## 8 Core Business Questions Addressed in the Notebook
1. **Product Categories & Revenue Concentration**: Which product categories and products generate the highest revenue, and how concentrated is revenue? *(Bar chart + Pareto chart)*
2. **Revenue Over Time & Seasonality**: How does revenue change over time, and are there identifiable monthly or seasonal patterns? *(Time-series line chart + Heatmap)*
3. **Customer Revenue Concentration**: Which customers generate the highest revenue, and what percentage of total revenue comes from the top 20% of customers? *(Pareto chart)*
4. **Frequency vs. Spending**: Is there a relationship between customer purchase frequency and total spending? *(Scatter plot + Regression line)*
5. **RFM Score Distribution**: How are customers distributed across different purchasing behaviors based on Recency, Frequency, and Monetary scores? *(RFM segmentation heatmap)*
6. **Customer Cohort Retention**: How does customer retention change over time, and what percentage of customers return after their first purchase? *(Cohort retention heatmap)*
7. **Segment Revenue & Inactivity**: Which customer segments contribute the most revenue, and which segments have the highest inactivity rates? *(Grouped bar chart)*
8. **Active vs. Inactive Behavioral Comparison**: Do inactive customers demonstrate significantly different purchasing behavior compared with active customers? *(Box plot + Statistical comparison)*

---

## Repository Structure
```text
Walmart_dashboard/
├── walmart_sales_analysis.ipynb       # Comprehensive root notebook answering the 8 analytical questions
├── outputs/                           # Generated charts and summary tables
├── .gitignore                         # Git ignore configuration
├── LEARNING_GUIDE.md                  # Standalone pedagogical learning guide
├── README.md                          # Project documentation
├── requirements.txt                   # Python package dependencies
├── EcommerceDashboardData.csv         # Processed dataset with RFM and Churn metrics
└── walmart_sales.csv                  # Raw dataset
```

---

## Setup & Installation

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd Walmart_dashboard
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Launch Jupyter Notebook**:
   ```bash
   jupyter notebook walmart_sales_analysis.ipynb
   ```
