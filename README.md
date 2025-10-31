

# 🍴 QuickBite Crisis Impact Analysis — Power BI | SQL | DAX

[![Live Dashboard](https://img.shields.io/badge/View-Live%20Dashboard-blue?style=for-the-badge\&logo=powerbi)](https://app.powerbi.com/view?r=eyJrIjoiNDFmMzkyNmYtMDE0NC00MzZlLWI1MWMtMmY3NmUxZDU3ZThiIiwidCI6IjNiYTNhODMxLTFkMzItNDA4My1hMzBjLWQ0YTk0NGYzNWI3ZSJ9)


---

## 📊 Project Overview

**QuickBite Express** — a Bengaluru-based food-tech startup — faced a major crisis in **June 2025**.
A viral food safety incident and week-long delivery outage during the monsoon season led to:

* ⚠️ **48% drop in daily orders**
* 📉 Rising **cancellation rates** & customer distrust
* 🍴 Partner restaurant churn
* 💰 **Tripled Customer Acquisition Cost (CAC)**

This project performs a **Crisis Impact Analysis** and builds a **data-driven recovery dashboard** using **Power BI, SQL, and DAX**.

---

## 🧭 Problem Statement

QuickBite management needed insights to:

1. Identify **recoverable customer segments**.
2. Compare **Pre-Crisis (Jan–May)** vs **Crisis (Jun–Sep)** performance.
3. Assess **delivery operations** (SLA, delays, cancellations).
4. Recommend **targeted loyalty campaigns**.
5. Track **restaurant churn and partner performance**.
6. Analyze **customer sentiment** post-crisis.

---

## 🧩 Dataset & Metadata

| Table                       | Description                                               |
| --------------------------- | --------------------------------------------------------- |
| `dim_customer`              | Customer profile — city, signup date, acquisition channel |
| `dim_restaurant`            | Restaurant details — cuisine type, city, status           |
| `dim_delivery_partner`      | Partner data — vehicle, city, rating                      |
| `fact_orders`               | Orders with timestamps, revenue, cancellations            |
| `fact_delivery_performance` | SLA and delivery time metrics                             |
| `fact_order_items`          | Item details with pricing and discounts                   |
| `fact_ratings`              | Ratings, review text, sentiment scores                    |

---

## ⚙️ Tools & Technologies

🧮 **Power BI Desktop / Service** — Dashboard design & modeling
🗃️ **SQL (PostgreSQL)** — Data transformation & analysis
⚙️ **Power Query (M)** — ETL & data cleaning
🧠 **DAX** — KPIs & time-intelligence calculations
📊 **Excel** — Data validation & pre-analysis

---

## 🧠 Key Insights

### 1️⃣ Orders & Revenue

* Orders fell **48%**, revenue **46%** during the crisis.
* **AOV** remained stable → drop due to lower demand, not pricing.
* Decline started **June 2025**, aligning with viral event.

### 2️⃣ City Performance

* Worst-hit: **Bengaluru, Mumbai, Delhi, Pune, Hyderabad**.
* Tier-1 cities experienced sharper decline due to social exposure.

### 3️⃣ Restaurant Analysis

* 10 major restaurants (≥50 pre-crisis orders) lost >60% of volume.
* **Cloud kitchens** proved more resilient than dine-in brands.

### 4️⃣ Delivery Metrics

* **Cancellations:** 7.5% → 19%
* **Avg Delivery Time:** 29 → 41 mins
* **SLA Compliance:** down 18%

### 5️⃣ Ratings & Sentiment

* Ratings dropped **4.3 → 3.6**.
* Top negative keywords: *delay, cold food, unsafe*.

### 6️⃣ Customer Retention

* 27% of loyal customers stopped ordering.
* 58% of churned users rated >4.5 (potential to recover).
* Top 5% spenders reduced frequency by **62%**.

---

## 📈 Power BI Dashboard Design

| Page                           | Focus Area           | Key Visuals           |
| ------------------------------ | -------------------- | --------------------- |
| **1️⃣ Executive Summary**      | Orders, Revenue, AOV | KPI Cards, Line Chart |
| **2️⃣ City Impact**            | City-wise % decline  | Map, Column Chart     |
| **3️⃣ Restaurant Performance** | Top 10 declines      | Scatter, Table        |
| **4️⃣ Delivery SLA**           | SLA vs Delays        | Clustered Bar, Line   |
| **5️⃣ Ratings & Sentiment**    | Reviews & keywords   | Word Cloud, Line      |
| **6️⃣ Loyalty Impact**         | Loyal user churn     | Cards, Table          |
| **7️⃣ High-Value Customers**   | Spend trends         | Scatter, Bars         |

🖤 **Theme:** Dark mode with Neon Blue & Orange
🧭 **Navigation:** Top bar with page buttons for storytelling

---

## 🧮 Key DAX Measures

```DAX
Total Orders = COUNTROWS('fact_orders')

Total Revenue =
SUMX('fact_orders',
'fact_orders'[subtotal_amount] +
'fact_orders'[delivery_fee] -
'fact_orders'[discount_amount])

PreCrisis Orders =
CALCULATE([Total Orders],
FILTER(ALL('Calendar'),
'Calendar'[Date] >= DATE(2025,1,1) &&
'Calendar'[Date] <= DATE(2025,5,31)))

Crisis Orders =
CALCULATE([Total Orders],
FILTER(ALL('Calendar'),
'Calendar'[Date] >= DATE(2025,6,1) &&
'Calendar'[Date] <= DATE(2025,9,30)))

% Decline in Orders =
VAR Pre = [PreCrisis Orders]
VAR Cri = [Crisis Orders]
RETURN IF(Pre > 0, DIVIDE(Pre - Cri, Pre))
```

---

## 💡 Recommendations

**Immediate (0–2 weeks):**
✅ “SafeBite” campaign with verified food safety partners.
✅ Personalized credits for high-rating churned users.

**Short Term (2–8 weeks):**
🔁 Retain top 10 partner restaurants.
🚚 Incentivize riders to boost SLA compliance.

**Medium Term (8–16 weeks):**
💳 Launch loyalty rewards.
📈 Predict churn through sentiment & frequency analysis.

---

## 🎥 Live Demo



💻 **GitHub Repository:**
👉 [Explore Full Project & DAX Code](https://github.com/Nikhillonkar19-code/QuickBite-Crisis-Impact-Analysis)

---

## 🧾 Dashboard Previews

### 🧩 Cover Page

![Cover Page](https://github.com/Nikhillonkar19-code/QuickBite-Crisis-Impact-Analysis/blob/main/rpc%20(1)_Cover_page.png)

### 📊 Executive Summary

![Executive Summary](https://github.com/Nikhillonkar19-code/QuickBite-Crisis-Impact-Analysis/blob/main/rpc%20\(2\)_Executive_Summary.jpg)

### 🏙️ Customer & City Detail

![Customer & City Detail](https://github.com/Nikhillonkar19-code/QuickBite-Crisis-Impact-Analysis/blob/main/rpc%20\(3\)_Customer_%26_City_Detail.jpg)

### 👥 Customer Lifetime Decline Analysis

![Customer Lifetime Decline Analysis](https://github.com/Nikhillonkar19-code/QuickBite-Crisis-Impact-Analysis/blob/main/rpc%20\(4\)_Customer_Lifetime_Decline_Analysis.jpg)

### 💡 Professional Insight Summary

![Insight Summary](https://github.com/Nikhillonkar19-code/QuickBite-Crisis-Impact-Analysis/blob/main/rpc%20(5)_Insight_Summary.jpg)

---

## 🧑‍💻 Author

**Nikhil Lonkar**
📊 Data Analyst | Power BI Developer
📍 Nashik, India

🔗 [LinkedIn](https://linkedin.com/in/your-link) | [GitHub](https://github.com/Nikhillonkar19-code)

---

### 🏁 Outcome

A data-driven roadmap to help **QuickBite recover 40–50% of lost demand** in 3 months through
**customer engagement, partner retention, and delivery optimization.**

---

