# customer_behavior_analysis_workflow
Customer Behavior Analysis for Business Insights and Decision-Making.The goal is to support business planning and management decision-making through data-driven analysis, SQL queries, and interactive dashboards.
# Customer Behavior Analysis for Business Insights and Decision-Making

##  Project Overview
This project focuses on cleaning, analyzing, and visualizing customer shopping behavior data to generate actionable business insights. The goal is to support **business planning and management decision-making** through data-driven analysis, SQL queries, and interactive dashboards.

The project covers the **full data analytics lifecycle**, from raw data cleaning to insight-driven recommendations.

---

##  Business Problem
Organizations collect large volumes of customer data but often struggle to translate it into meaningful insights.  
This project aims to:
- Understand customer purchasing behavior
- Identify trends and high-value customer segments
- Support strategic decisions in marketing, product management, and customer retention

---

##  Tools & Technologies
- **Python** (Pandas, NumPy, Matplotlib)
- **MySQL** (Data storage, querying, views)
- **Power BI** (Interactive dashboards)
- **GitHub** (Version control & documentation)

---

##  Project Workflow

### 2 Data Cleaning (Python)
The raw dataset was cleaned using Python to ensure accuracy and consistency.

Key steps included:
- Handling missing values (median-based imputation)
- Standardizing categorical values
- Detecting and validating outliers using business logic
- Converting purchase frequency categories into numeric indicators
- Creating derived fields such as age groups and purchase frequency in days

The cleaned dataset was then exported to:
- MySQL database
- CSV/Excel files for reuse

---

### 2 Exploratory Data Analysis (Python)
Exploratory analysis was performed to understand:
- Customer demographics
- Spending behavior
- Purchase frequency patterns
- Review ratings and repeat purchases

This step helped guide the SQL queries and dashboard design.

---

### 3️ Data Storage & SQL Analysis (MySQL)
Two databases were created:
- `datacleaning` – raw data
- `cleaneddata` – cleaned and analysis-ready data

A SQL **VIEW** was created to optimize Power BI performance:
```sql
CREATE VIEW vw_customer_behavior AS
SELECT
    customer_id,
    age,
    gender,
    category,
    purchase_amount,
    season,
    previous_purchases,
    frequency_of_purchases,
    purchase_frequency_days,
    review_rating,
    subscription_status,
    discount_applied,
    age_group,
    payment_method
FROM customer_behavior_clean;
