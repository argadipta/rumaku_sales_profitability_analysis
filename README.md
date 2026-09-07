# Rumaku Profitability Analysis

## 📌 Project Overview
End-to-end business analysis project: from raw data riddled with quality issues to an interactive dashboard — uncovering the drivers behind a sharp profit decline at a fictional furniture retailer ("Rumaku") in Q3 2025.

<img width="1050" height="583" alt="Screenshot 2026-09-07 142905" src="https://github.com/user-attachments/assets/2e1e05f4-db59-4573-8f01-44db0b60f069" />


---

## 🎯 Background
The Head of Retail at a furniture company noticed a sharp profit decline in the quarterly financial report and requested a deep-dive investigation to answer 5 questions:

1. When did the sharpest profit decline occur, and how large was it?
2. Was it driven by product mix, sales channel, or discount policy?
3. Which product categories were most affected?
4. Is the Online channel still profitable after accounting for shipping costs?
5. What strategic recommendations can be made?

*(This dataset is a practice case study, not real company data.)*

---

## 🛠️ Tools & Technologies
* **Python** (Pandas, NumPy)
* **SQL / Google BigQuery**
* **Power BI**
* **Google Colab**

---

## 🔄 Analytical Process
The project follows these main stages:

1. Data Loading
2. Data Inspection
3. Data Cleaning, Validation & Quality Audit
4. Exploratory Data Analysis (EDA)
5. KPI Analysis
6. Product & Category Analysis
7. Sales Channel Analysis
8. Data Visualization (Power BI)
9. Business Insight
10. Business Recommendations

---

## 📊 Key KPIs
The analysis focuses on the following business metrics:
* Revenue
* Orders
* Cost
* Net Profit
* Profit Margin
* Average Discount
* Product Category Performance
* Sales Channel Performance

---

## 🔎 Key Findings

### Revenue & Profitability
* Revenue declined by **61.01% in Q3 2025** compared with Q2 2025.
* Net profit declined by **66.53%** compared with Q2 2025.
* Profit margin decreased by **5.47 percentage points**.

### Product Categories
* **Beds & Mattresses (Kasur & Springbed)**
* **Lighting (Pencahayaan)**
* **Cabinets & Shelving (Lemari & Rak)**

These three categories contributed approximately **92.62% of the total profit decline**.

### Sales Channel
Online sales remained profitable, but its margin declined from **40.07% to 30.42%**.

### Discount
Average discount increased from **8.05% to 8.79%**, a mild increase that does not appear to be the primary driver of the margin decline.

---

## 🐛 Data Quality Issues Found & Fixed
Before the numbers above could be trusted, the raw data was audited and **5 data quality issues** were uncovered — one of which was significant enough to change the analysis's conclusions.

1. **🔴 Date-parsing bug (most critical):** `format="mixed", dayfirst=True` swapped month and day for ISO-formatted dates after separator standardization, affecting 31.4% of rows and shifting 3,157 rows into the wrong quarter.
2. **Cancelled/returned orders counted as revenue:** `order_status` was never used to filter the data; 8.43% of transactions (Rp10.6B) were incorrectly included.
3. **Duplicate channel labels:** "Toko Fisik" and "Offline" were confirmed (via `store_id`) to be the same physical-store channel, but were treated as two separate categories.
4. **`payment_method` standardization bug:** column ordering split raw "COD" values into two categories, "Cod" and "COD".
5. **Untreated shipping-cost outliers:** 6 rows with shipping costs 14x–83x the item price were flagged via IQR but never corrected, distorting net profit in the exact quarter under investigation.

*(Full before/after details in the notebook's data cleaning section.)*

---

## 💡 Business Insight

The decline in profitability was driven by both a substantial contraction in sales volume and margin compression — not by one factor alone. The decline was heavily concentrated in three product categories, while the Online channel, despite a margin decline, remained profitable and was not the primary driver.


---

## 🎯 Business Recommendations
Based on the analysis, the following actions are recommended:

1. **Investigate the decline in sales volume** to understand the main factors behind the Q3 revenue contraction.
2. **Focus margin-recovery efforts** on Beds & Mattresses, Lighting, and Cabinets & Shelving — the three categories driving 92.62% of the decline.
3. **Review Online channel economics** given the margin decline from 40.07% to 30.42%, even though it remains profitable.
4. **Apply targeted rather than broad discounting** to protect sales volume without further compressing margin.
5. **Monitor discount effectiveness** going forward to ensure any increase in discounting generates sufficient additional volume to justify its margin impact.


---

## 📈 Dashboard

The project includes a Power BI dashboard designed to monitor:

* Revenue & Net Profit trends by quarter
* QoQ Profit Change %
* Net Profit by Category
* Online channel Profit Margin trend

Dashboard screenshots and supporting visualizations will be added to this repository.

---

## 📓 Notebook

The complete Python analysis can be found in:
**`https://colab.research.google.com/drive/1nbSnGXmPEzfBu56wQ01hmhAEuKCW7j9h`**

The notebook contains the full workflow: data loading, data quality audit & cleaning, exploratory analysis, KPI calculations, visualizations, and business findings.

---

## 👤 Author
**Arga Dipta Putratama, S.T.**
Junior Data Analyst | Python | SQL | Excel | Power BI

* LinkedIn: https://linkedin.com/in/argadipta
* GitHub: https://github.com/argadipta
