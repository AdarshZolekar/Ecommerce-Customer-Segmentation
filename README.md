## Ecommerce Customer Segmentation

![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![RFM Analysis](https://img.shields.io/badge/RFM%20Analysis-Customer%20Segmentation-blueviolet?style=for-the-badge)
![Dataset](https://img.shields.io/badge/Dataset-500K%2B%20Records-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

This project applies **Recency, Frequency, and Monetary (RFM)** analysis to segment e-commerce customers based on their purchasing behavior, using SQL as the primary analytical tool.
The analysis is built on a real-world **UK-based e-commerce transactions dataset** of 500K+ records, imported into MySQL, cleaned and engineered into meaningful customer metrics.
Each customer is scored and categorized into segments such as Champions, Loyal Customers, At-Risk Big Spenders and enabling data-driven targeting strategies.
The final segmented output is visualized through an **interactive Power BI dashboard**, providing business stakeholders with actionable insights on customer value and retention.
This end-to-end project demonstrates practical skills across data cleaning, SQL feature engineering, RFM modeling and business intelligence reporting.

---

## Business Objective
To segment customers for **targeted marketing** by identifying:
- **Champions**
- **Loyal Customers**
- **At Risk / Lost Customers**
- **New Customers**
- **Big Spenders at Risk**.

---

## Dataset Summary
- **Source**: Kaggle E-Commerce UK Dataset
- **Link** : https://www.kaggle.com/datasets/carrie1/ecommerce-data/data
- **Records**: 500K+ transactions
- **Fields**: InvoiceNo, Product Description, Quantity, UnitPrice, CustomerID, Country, InvoiceDate.

---

## Process Summary

### 1. Data Cleaning
- Removed null and blank descriptions & customer IDs
- Removed duplicates using composite key
- Handled returns based on `InvoiceNo LIKE 'C%'`

### 2. Feature Engineering
- Created table `edata_clean`, `edata_cancelled`; created view `edata_customer_type`
- Calculated RFM metrics:
  - **Recency**: Days since last purchase
  - **Frequency**: Count of unique invoices
  - **Monetary**: Total spend per customer

### 3. RFM Scoring
- Scores (1–4) assigned for each metric based on thresholds
- Joined into final view `edata_rfm_segmented`

### 4. Customer Segmentation
Applied conditional logic to tag each customer into:

| Segment              | Criteria (R, F, M)         |
|----------------------|----------------------------|
| Champions            | R=4, F=4, M=4              |
| Loyal Customers      | R≥4, F≥3, M≥3              |
| Loyal but Slipping   | R≤2, F=4, M=4              |
| Big Spenders at Risk | R≤2, F≤2, M≥3              |
| New Customers        | R=4, F=1, M=1              |
| Lost                 | R=1, F=1, M=1              |
| Others               | Everything else            |

---

## Sample Output

| CustomerID | Recency | Frequency | Monetary | Segment           |
|------------|---------|-----------|----------|--------------------|
| 12748.0    | 3       | 107       | 11773.76 | Champions          |
| 14911.0    | 1       | 80        | 49217.04 | Champions          |
| 16013.0    | 16      | 25        | 15321.32 | Loyal Customers    |
| 17850.0    | 216     | 34        | 5391.21  | Others             |

---

## Power BI Dashboard Overview

The cleaned SQL output was imported into Power BI to create an **interactive business dashboard**.

### Page 1 – Customer Overview

- KPIs: Total Revenue, Total Customers, New vs Returning %
- Monthly Revenue Trends
- Pie Chart: Customer Type Distribution
- Filter by Customer Type

### Page 2 – RFM Segmentation Dashboard

- KPI Cards: Recency, Frequency, Monetary
- Bar Chart: Segment Count
- Line Chart: Revenue per Segment by Month
- Table: Customers per Segment with drillthrough.

### Page 3 – Customer Drillthrough View

- Customer Details by RFM Segment
- Cross-filtering using drillthrough
- Dynamic visuals updated based on the selected customer.

---

## Tools Used
- **MySQL Workbench**
- CSV Import & Table Creation
- SQL Views & Case Logic
- Exported final table for Power BI dashboard.

---

## SQL - Key Skills Demonstrated
- Data Cleaning (NULLs, Duplicates, Returns)
- SQL Feature Engineering
- Customer Segmentation via RFM
- Business Logic Implementation
- Preparation for Power BI Visualization.

---

## Power BI - Key Skills Demonstrated
- DAX Measures for KPIs
- Drillthrough & Cross-filtering
- Page navigation & conditional formatting
- Data storytelling with business context.

---

## License

This project is open-source under the MIT License.

---

## Contributions

Contributions are welcome!

- Open an issue for bugs or feature requests

- Submit a pull request for improvements.


<p align="center">
  <a href="#top">
    <img src="https://img.shields.io/badge/%E2%AC%86-Back%20to%20Top-blue?style=for-the-badge" alt="Back to Top"/>
  </a>
</p>



