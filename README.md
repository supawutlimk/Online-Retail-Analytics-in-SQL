# Online-Retail-Analytics-in-SQL

# 📊 Online Retail Analytics in SQL

This project analyzes **e-commerce transaction data** (UCI Online Retail dataset) using **SQLite and SQL queries**. The goal is to uncover insights into **sales performance** and **customer retention** that would help a business like Oda (online grocery delivery) improve commercial and customer outcomes.

---

## 🔹 Business Context

E-commerce companies operate with thin margins and rely heavily on customer loyalty. To succeed, they must:

- Understand **what drives revenue** (top products, top customers, seasonal trends).
- Track **customer retention** to ensure that first-time buyers return.

This project demonstrates how SQL can be used to answer these questions directly from raw transaction data.

---

## 🔹 Data Overview

- **Source:** https://www.kaggle.com/datasets/carrie1/ecommerce-data
- **Rows:** 541,909 transactions (Dec 2010 – Dec 2011)
- **Columns:** InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, Country
- **Cleaning:** Excluded cancelled invoices (InvoiceNo starting with “C”), negative quantities, and missing CustomerIDs.
- **Final sample size:** ~530k clean sales rows

---

## 🔹 Business Questions

### Part 1: Sales Performance

- What is the monthly revenue trend?
- Which products generate the highest revenue?
- What is the average order value (AOV) and units per order over time?
- Which countries drive sales?

### Part 2: Customer Retention

- Do customers return after their first purchase?
- How does retention vary by cohort month?
- What percentage of customers are still active after 1, 2, or 3 months?

---

## 🔹 Methods

- Data stored in **SQLite** (`retail.db`).
- Clean view `v_sales_clean` created to filter out cancellations and invalid rows.
- SQL queries written in Jupyter with `ipython-sql`.
- Results visualized with **Matplotlib** and **heatmaps**.

---

## 🔹 Key Findings

### 📈 Monthly Revenue

Revenue is **seasonal**, with peaks in November 2011 (holiday shopping). The highest AOV is from December 2011 with the AOV of 779.87. In addition, the UK drives the most sales with revenue up to 9,025,222 or approximately 84.64 % of the total revenue.

![Monthly Revenue](https://chatgpt.com/c/download%20(1).png)

### 🛍️ Top Products by Revenue

Revenue is highly concentrated in a small number of SKUs, led by **DOTCOM POSTAGE** , **REGENCY CAKESTAND 3 TIER and PAPER CRAFT, LITTLE BIRDIE**.

![Top Products](https://chatgpt.com/c/download.png)

### 🔄 Customer Retention

Retention is strong in month 0 (100%) but drops sharply. By month 3, less than 30% of customers are still active, highlighting churn risk. Especially, the customers who did the firsr puchae in September 2011, by month 3, the retention drops to less than 2% - however, this might be due to the customer in this cohort did a holiday shopping earlier than the others.

![Cohort Retention](https://chatgpt.com/c/download%20(2).png)

---

## 🔹 Recommendations

- **Boost retention**: Introduce loyalty programs, email reminders, or subscriptions to improve repeat purchases.
- **Double down on top products**: Focus promotions and inventory on the top 10 revenue-generating products.
- **Monitor seasonality**: Plan campaigns and stock levels around the Q4 spike in demand.
