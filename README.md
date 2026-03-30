# 📊 Customer Churn Analysis Dashboard | Power BI

## Project Overview

An interactive **Power BI dashboard** analyzing customer churn for a telecom company. Analyzed **7,043 customer records** to identify key drivers of churn and provide actionable business recommendations.

**Live Dashboard Preview**: [Screenshots Below]

---

## 🎯 Business Problem

Telecom companies lose millions in revenue due to customer churn. This dashboard helps identify:
- **Who** is leaving
- **Why** they are leaving
- **What** actions can reduce churn

---

## 📈 Key Insights

| Metric | Value |
|--------|-------|
| **Total Customers** | 7,043 |
| **Total Churned** | 2,000+ |
| **Churn Rate** | 26.5% |
| **Avg Tenure** | 32.4 months |

### Top Churn Drivers

| Factor | Churn Rate | Impact |
|--------|------------|--------|
| Month-to-month contract | 42% | 🔴 High |
| Electronic check payment | 45% | 🔴 High |
| No online security | 3x higher | 🔴 High |
| Fiber optic internet | 41% | 🟡 Medium |
| First 12 months tenure | Highest | 🟡 Medium |

### Retention Opportunities

| Contract Type | Churn Rate | Opportunity |
|---------------|------------|-------------|
| Two-year contract | 3% | ✅ Loyal customers |
| One-year contract | 11% | ✅ Convert to 2-year |
| Month-to-month | 42% | 🔴 Target for conversion |

---

Customer-Churn-Analysis-Dashboard/
│
├── Customer_Churn_Dashboard.pbix # Power BI dashboard file
├── README.md # Project documentation (this file)
├── data/
│ └── telco_customer_churn.csv # Raw dataset
├── images/
│ ├── dashboard_overview.png # Main dashboard preview
│ ├── churn_by_contract.png # Contract analysis
│ ├── churn_by_payment.png # Payment method analysis
│ └── churn_by_tenure.png # Tenure analysis
├── docs/
│ ├── DAX_Measures.md # All DAX formulas documented
│ ├── Data_Cleaning_Steps.md # Power Query transformations
│ └── Business_Recommendations.md # Actionable insights
└── LICENSE # MIT License


---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Power BI Desktop** | Dashboard development & visualization |
| **Power Query** | Data cleaning & transformation |
| **DAX (Data Analysis Expressions)** | Calculated measures & KPIs |
| **Excel** | Initial data exploration |
| **Git/GitHub** | Version control & portfolio hosting |

---

## 📊 Dashboard Pages

### Executive Summary (One-Page Layout)

| Section | Visual | Purpose |
|---------|--------|---------|
| **KPI Cards** | 4 cards | Total Customers, Total Churned, Churn Rate, Avg Tenure |
| **Contract Analysis** | Bar Chart | Churn by Month-to-month, One year, Two year |
| **Payment Analysis** | Bar Chart | Churn by Electronic check, Mailed check, Bank transfer, Credit card |
| **Internet Service** | Bar Chart | Churn by Fiber optic, DSL, No internet |
| **Online Security** | Bar Chart | Churn by Yes vs No |
| **Tenure Analysis** | Line Chart | Churn rate by tenure groups |
| **Demographics** | Donut Charts | Churn by Gender, Senior Status, Partner |

---

## 📐 DAX Measures Created

### Core KPIs

```dax
Total Customers = COUNTROWS(telco_churn)

Total Churned = CALCULATE(COUNTROWS(telco_churn), telco_churn[Churn] = "Yes")

Churn Rate % = DIVIDE([Total Churned], [Total Customers]) * 100

Avg Tenure = AVERAGE(telco_churn[tenure])
```

Churn by Contract
```dax
MTM Churn = CALCULATE([Total Churned], telco_churn[Contract] = "Month-to-month")

OneYear Churn = CALCULATE([Total Churned], telco_churn[Contract] = "One year")

TwoYear Churn = CALCULATE([Total Churned], telco_churn[Contract] = "Two year")
```

Churn by Service
```dax
NoSecurity Churn = CALCULATE([Total Churned], telco_churn[OnlineSecurity] = "No")

NoTechSupport Churn = CALCULATE([Total Churned], telco_churn[TechSupport] = "No")
```
Churn by Payment
```dax
ECheck Churn = CALCULATE([Total Churned], telco_churn[PaymentMethod] = "Electronic check")

MailedCheck Churn = CALCULATE([Total Churned], telco_churn[PaymentMethod] = "Mailed check")
```
Data Cleaning Steps
Data Type Validation – Ensured tenure, MonthlyCharges, TotalCharges as numbers

Handle Missing Values – Replaced blank TotalCharges with 0

Create Tenure Groups – Grouped tenure into 6 categories (0-12, 13-24, etc.)

Create Senior Status – Converted SeniorCitizen to "Senior"/"Non-Senior"

Column Optimization – Removed unnecessary columns (customerID)

Business Recommendations
Issue	Recommendation	Expected Impact
Month-to-month churn (42%)	Offer discounts for 1-2 year contracts	30-40% reduction
Electronic check churn (45%)	Promote autopay with 5% discount	20-25% reduction
No online security	Bundle security with internet plans	15-20% reduction
Fiber optic churn (41%)	Investigate pricing/service quality	10-15% reduction
New customer churn	Strengthen onboarding program	20-25% reduction

 How to Use This Dashboard
Option 1: View the Dashboard
Download Customer_Churn_Dashboard.pbix

Open with Power BI Desktop (free)

Explore interactive slicers and visuals

Option 2: Connect Your Own Data
Replace dataset with your customer data

Update column names in DAX measures

Refresh Power Query transformations

Customize visuals for your business context

What I Learned
DAX Mastery – Created 20+ measures for churn analysis

Power Query – Data transformation and tenure grouping

Business Intelligence – Translating data into actionable recommendations

Visual Design – One-page dashboard with clear hierarchy

GitHub Portfolio – Professional project documentation

🔗 Connect With Me
I'm a BI Analyst & Commercial Analyst passionate about turning data into business insights.

Email: safa.moeen4545@gmail.com

LinkedIn: [linkedin.com/in/safa-moeen](https://www.linkedin.com/in/safa-moeen-90b7bb261/)

Open to BI Analyst, Commercial Analyst, and freelance opportunities!
