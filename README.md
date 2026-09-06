import pypandoc, os, textwrap

readme = r"""# PureCo Order & Return Performance Dashboard

## 📊 Project Overview

This project analyzes **PureCo's e-commerce order data** to understand order performance, returns, cancellations, delivery time, and customer behavior.

The project was created in **Microsoft Excel** using data cleaning, pivot tables, KPI calculations, and an interactive dashboard.

### Business Objective

The main objective is to answer questions such as:

- What percentage of orders are completed, returned, or cancelled?
- Which product categories have the highest return rates?
- What are the major reasons for product returns?
- How long does order delivery take on average?
- Which countries and customer segments show different order/return patterns?
- How can the business use these insights to improve operations?

---

## 🗂️ Project Structure

| Sheet | Purpose |
|---|---|
| **DASHBOARD** | Final KPI dashboard showing order and return performance |
| **Raw_Data** | Original/raw dataset containing inconsistent values and data-quality issues |
| **Raw_Data (2)** | Cleaned and standardized dataset used for analysis |
| **Table2** | Structured Excel table used for analysis/pivot tables |
| **Sheet2** | Supporting pivot tables and KPI calculations |

---

## 🧹 Data Cleaning

The raw dataset contained several data-quality issues. The data was cleaned before creating the dashboard.

### Cleaning activities

- Standardized country names and country codes
- Standardized product category names
- Standardized order status values such as `Completed`, `Returned`, and `Cancelled`
- Standardized shipping method values
- Standardized product names
- Removed duplicate records
- Checked missing values
- Reviewed return-reason fields
- Identified invalid delivery-day values
- Prepared the cleaned data for pivot-table analysis

The raw dataset contains **894 records**, including duplicate Order IDs and inconsistent formatting. The cleaned analysis data was prepared after removing duplicate records and standardizing fields.

---

## 📌 Key KPIs

The dashboard focuses on the following performance indicators:

### 1. Return Rate
Percentage of orders that were returned.

**Formula:**

`Return Rate = Returned Orders / Total Orders × 100`

### 2. Cancellation Rate
Percentage of orders that were cancelled.

**Formula:**

`Cancellation Rate = Cancelled Orders / Total Orders × 100`

### 3. Completion Rate
Percentage of orders successfully completed.

**Formula:**

`Completion Rate = Completed Orders / Total Orders × 100`

### 4. Average Delivery Days
Average number of days required to deliver an order.

### 5. Missing Return Reason %
Percentage of returned orders where the return reason is missing.

### 6. Return Rate by Category
Comparison of return rates across product categories such as:

- Body Care
- Hair Care
- Skin Care
- Wellness

---

## 📈 Dashboard Analysis

The dashboard provides a quick view of:

- Overall order status
- Return performance
- Cancellation performance
- Average delivery time
- Return rate by product category
- Return reasons
- Country-level performance
- Customer/order trends

Pivot tables and Excel calculations were used to create the supporting analysis.

---

## 🔍 Key Findings

Based on the cleaned analysis:

- **Completed orders** represent the largest share of orders.
- **Returned orders** are a smaller but important portion of total orders.
- **Cancelled orders** also contribute to lost order volume.
- Return performance differs across product categories.
- Return reasons can help identify product-quality, description, or customer-expectation issues.
- Delivery time is an important operational KPI that can be monitored alongside return and cancellation rates.

> Note: KPI values shown in this README may differ if the workbook is updated or dashboard filters/slicers are changed.

---

## 🛠️ Tools & Skills Used

- **Microsoft Excel**
- Data Cleaning
- Data Standardization
- Excel Tables
- Pivot Tables
- KPI Calculations
- Dashboard Design
- Data Analysis
- Business Insights

---

## 📁 Dataset Columns

The analysis dataset contains fields such as:

- `OrderID`
- `OrderDate`
- `CustomerID`
- `Country`
- `ProductCategory`
- `ProductName`
- `Quantity`
- `UnitPrice_EUR`
- `OrderStatus`
- `ReturnReason`
- `ShippingMethod`
- `DeliveryDays`
- `CustomerType`

---

## 💡 Business Recommendations

Based on the analysis, PureCo can:

1. Investigate categories with relatively high return rates.
2. Track the most common return reasons and address recurring issues.
3. Improve product descriptions to reduce expectation-related returns.
4. Monitor delivery performance and investigate unusually long delivery times.
5. Compare return and cancellation rates across customer types and countries.
6. Regularly update the dashboard to monitor operational performance.

---

## 🚀 How to Use the Project

1. Open the Excel workbook.
2. Go to the **DASHBOARD** sheet.
3. Review the KPI cards and charts.
4. Use the supporting pivot tables in **Sheet2** for detailed analysis.
5. Use **Raw_Data (2)** / **Table2** to review the cleaned analysis data.
6. Update the source data and refresh the pivot tables when new data is added.

---

## 📌 Project Type

**Excel Data Analytics / Business Intelligence Project**

**Focus:** E-commerce Order, Return & Delivery Performance

**Tool:** Microsoft Excel

---

## 👤 Author

**[Your Name]**

Add your name and LinkedIn profile here if you are using this project in your portfolio.

"""
out="/mnt/data/README.md"
pypandoc.convert_text(readme, 'md', format='md', outputfile=out, extra_args=['--standalone'])
print(out, os.path.getsize(out))
