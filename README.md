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
## Churn Risk Category
Churn Risk Category = 
SWITCH(
    'Telco-Customer-Churn'[Churn Risk Score],
    3, "High Risk",
    2, "Medium Risk",
    "Low Risk"
)
## Churned Customers
Churned Customers = 
CALCULATE(
    DISTINCTCOUNT('Telco-Customer-Churn'[customerID]),
    'Telco-Customer-Churn'[Churn] = "Yes"
)
## Total Services
Total Services =
IF([PhoneService]="Yes",1,0) +
IF([MultipleLines]="Yes",1,0) +
IF([OnlineSecurity]="Yes",1,0) +
IF([OnlineBackup]="Yes",1,0) +
IF([DeviceProtection]="Yes",1,0) +
IF([TechSupport]="Yes",1,0) +
IF([StreamingTV]="Yes",1,0) +
IF([StreamingMovies]="Yes",1,0)
Business Insights Generated
Identified high churn-risk customers
Analyzed service adoption patterns
Compared churn across customer segments
Measured customer retention trends
Improved business decision-making with KPI tracking
Dashboard Highlights
Churn Rate KPI
Customer Segmentation
Monthly Charges Analysis
Contract Type Analysis
Internet Service Comparison
Service Combination Analysis
Project Outcome

This project demonstrates practical skills in:

Power BI Dashboard Development
DAX Formula Writing
Data Visualization
Business Intelligence
Customer Analytics
KPI Reporting
Author

Dippu Sai Dinesh Goud


---

# Recommended GitHub Repository Structure

```text
Telco-Customer-Churn-Analysis/
│
├── Dashboard.pbix
├── Dataset.csv
├── README.md
├── Screenshots/
│   ├── Dashboard1.png
│   ├── Dashboard2.png
│
└── Presentation/
    └── Project_Presentation.pptx
insights.

Key Skills Used:
✔ Power BI
✔ DAX
✔ Data Cleaning
✔ KPI Reporting
✔ Customer Analytics
✔ Dashboard Design
