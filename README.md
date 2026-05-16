# Telco Customer Churn Analysis – Power BI Project

## Project Overview
This project focuses on analyzing customer churn behavior using Microsoft Power BI.  
The dashboard provides insights into customer retention, churn risk segmentation, service usage patterns, and revenue-related KPIs.

The objective of this project is to help businesses identify high-risk customers and improve retention strategies through data-driven insights.

---

# Tools & Technologies Used

- Microsoft Power BI
- Power Query
- DAX (Data Analysis Expressions)
- Excel / CSV Dataset
- Data Cleaning & Transformation

---

# Key Features

- Customer Churn Analysis
- Churn Risk Segmentation
- KPI Dashboard
- Service Subscription Analysis
- Customer Demographics Insights
- Interactive Filters & Slicers
- DAX-Based Business Metrics

---

# DAX Formulas Implemented

## Churn Risk Score
```DAX
Churn Risk Score = 
VAR tenure = 'Telco-Customer-Churn'[tenure]
VAR charges = 'Telco-Customer-Churn'[MonthlyCharges]
RETURN
SWITCH(
    TRUE(),
    tenure <= 12 && charges >= 70, 3,
    tenure <= 24 && charges >= 50, 2,
    1
)
