# Stylo-Retail-Operations-Dashboard-PowerBI

![Power
BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Measures-blue) ![Power
Query](https://img.shields.io/badge/Power%20Query-ETL-green) ![Retail
Analytics](https://img.shields.io/badge/Domain-Retail-purple)


#  Project Overview

Retail Operations Dashboard – Stylo Pakistan (Simulated)

An end-to-end Retail Operations Dashboard built in Microsoft Power BI, using a simulated dataset modeled on Stylo Pakistan, one of the country's leading fashion footwear and lifestyle retailers.

This project replicates a real-world retail analytics use case — transforming raw transactional data into an executive-ready decision-support tool. It's designed to help retail management track sales performance, monitor store-level operations, and uncover product-level insights through a fully interactive, KPI-driven reporting layer.
Business Objective
Retail leadership needs a single source of truth to answer questions like:

Which stores and regions are driving (or dragging) revenue?
How is the product portfolio performing across categories, seasons, and price points?
Where are the operational bottlenecks — stock, footfall, conversion — that need attention?

---

#  Business Problem

Retail companies generate thousands of transactions daily across multiple stores, products, and cities.

Management often struggles to answer questions such as:

- Which stores generate the highest sales?
- Which product categories drive revenue?
- Which products are most profitable?
- Which provinces perform best?
- How many products are being returned?
- What is the Average Order Value?
- Which sales channel contributes the most revenue?

The objective of this dashboard is to convert raw retail data into actionable business insights.

---

#  Tools & Technologies

- Microsoft Power BI Desktop
- Power Query
- DAX
- Data Modeling
- Star Schema
- Data Visualization

---

#  Dataset

The project uses a retail dataset containing:

### Fact Table

- FactSales

### Dimension Tables

- DimDate
- DimStore
- DimProduct
- DimCustomer
- DimEmployee
- DimPromotion
- DimPaymentMethod

--- 

#  Data Model

<img width="1622" height="969" alt="ChatGPT Image Jul 10, 2026, 09_37_33 AM" src="https://github.com/user-attachments/assets/de8adaea-b40c-474a-a65a-375ea068cf58" />

#  Dashboard Pages

---

#  Page 1 — Executive Overview

<img width="1153" height="675" alt="1" src="https://github.com/user-attachments/assets/d3beac89-e602-49ed-8ff2-953209b92c9b" />

This page provides management with a high-level overview of overall business performance.

## KPIs

| KPI | Value |
|------|--------|
| Total Sales | **286M** |
| Total Profit | **132.93M** |
| Profit Margin | **47%** |
| Total Orders | **26K** |
| Average Order Value | **10.98K** |
| Return Rate | **7%** |

## Visuals

- Monthly Sales Trend
- Sales by Product Category
- Sales by City
- Sales by Order Channel

## Business Insights

- Women's Shoes generated the highest sales.
- Store sales contributed approximately **80%** of total revenue.
- Online sales contributed approximately **20%**.
- Major cities dominated overall revenue.

---

#  Page 2 — Store Performance Dashboard

<img width="1136" height="629" alt="2" src="https://github.com/user-attachments/assets/eccd87af-cb0a-4cb7-a625-a04d8a1c27cd" />

This page evaluates the performance of individual stores.

## KPIs

| KPI | Value |
|------|--------|
| Total Stores | **60** |
| Average Sales per Store | **4.76M** |
| Average Profit per Store | **2.22M** |
| Average Rating | **4.05** |
| Total Customers | **5K** |
| Return Rate | **7%** |

## Visuals

- Store Performance Matrix
- Top 10 Stores by Sales
- Sales by Province
- Sales by City

## Business Insights

- Punjab generated the highest sales.
- Top-performing stores generated over **7M** in sales.
- Average customer rating remained above **4.0**.

---

#  Page 3 — Product Performance Dashboard

Analyzes products and product categories.

## KPIs

| KPI | Value |
|------|--------|
| Total Products | **250** |
| Total Categories | **7** |
| Average Product Sales | **1.14M** |
| Average Product Profit | **531.73K** |
| Average Selling Price | **4.97K** |
| Return Rate | **7%** |

## Visuals

- Top Products by Sales
- Sales by Product Category
- Profit by Category
- Sales Contribution by Material
- Sales by Gender
- Product Performance Table

## Business Insights

- Women's Shoes remained the highest-performing category.
- Silk products generated the largest material contribution.
- Female products represented approximately **75%** of total sales.

---

#  DAX Measures

## Total Sales

```DAX
Total Sales =
SUM(FactSales[NetSales])
```

---

## Total Profit

```DAX
Total Profit =
SUM(FactSales[Profit])
```

---

## Total Orders

```DAX
Total Orders =
DISTINCTCOUNT(FactSales[InvoiceID])
```

---

## Total Quantity

```DAX
Total Quantity =
SUM(FactSales[Quantity])
```

---

## Average Order Value

```DAX
Average Order Value =
DIVIDE(
    [Total Sales],
    [Total Orders]
)
```

---

## Profit Margin %

```DAX
Profit Margin % =
DIVIDE(
    [Total Profit],
    [Total Sales]
)
```

---

## Return Orders

```DAX
Return Orders =
CALCULATE(
    COUNTROWS(FactSales),
    FactSales[Returned] = "Yes"
)
```

---

## Return Rate %

```DAX
Return Rate % =
DIVIDE(
    [Return Orders],
    [Total Orders]
)
```

---

## Total Stores

```DAX
Total Stores =
DISTINCTCOUNT(DimStore[StoreID])
```

---

## Average Sales per Store

```DAX
Avg Store Sales =
DIVIDE(
    [Total Sales],
    [Total Stores]
)
```

---

## Average Profit per Store

```DAX
Avg Profit Store =
DIVIDE(
    [Total Profit],
    [Total Stores]
)
```

---

## Average Rating

```DAX
Average Rating =
AVERAGE(FactSales[Rating])
```

---

## Total Customers

```DAX
Total Customers =
DISTINCTCOUNT(FactSales[CustomerID])
```

---

## Total Products

```DAX
Total Products =
DISTINCTCOUNT(DimProduct[ProductID])
```

---

## Total Categories

```DAX
Total Categories =
DISTINCTCOUNT(DimProduct[Category])
```

---

## Average Product Sales

```DAX
Avg Product Sales =
DIVIDE(
    [Total Sales],
    [Total Products]
)
```

---

## Average Product Profit

```DAX
Avg Product Profit =
DIVIDE(
    [Total Profit],
    [Total Products]
)
```

---

## Average Selling Price

```DAX
Average Selling Price =
AVERAGE(FactSales[UnitPrice])
```

---

#  Interactive Filters

The dashboard supports dynamic filtering through:

- Year
- Month
- Province
- Store Type
- Category
- Material
- Membership Type
- Order Channel
- Store Name

All visuals interact automatically through cross-filtering.

---

#  Key Insights

- Total Revenue reached **286M**.
- Overall Profit reached **132.93M**.
- Profit Margin remained at **47%**.
- More than **26,000 orders** were analyzed.
- Women's Shoes generated the highest revenue.
- Punjab was the best-performing province.
- Store sales accounted for approximately **80%** of total revenue.
- Online sales represented approximately **20%**.
- Return Rate remained low at **7%**.
- Average customer rating remained above **4.0**.

---

#  Skills Demonstrated

- Power BI
- Power Query
- DAX
- Data Cleaning
- Data Modeling
- Star Schema
- Retail Analytics
- Business Intelligence
- KPI Development
- Dashboard Design
- Interactive Reporting
- Executive Reporting

---

#  Repository Structure

```
Stylo-Retail-Operations-Dashboard
│
├── Dashboard
│   └── Stylo Retail Operations Dashboard.pbix
│
├── Dataset
│   ├── FactSales.csv
│   ├── DimProduct.csv
│   ├── DimStore.csv
│   ├── DimCustomer.csv
│   ├── DimDate.csv
│   ├── DimEmployee.csv
│   ├── DimPromotion.csv
│   └── DimPaymentMethod.csv
│
├── Images
│   ├── Executive Overview.png
│   ├── Store Performance.png
│   └── Product Performance.png
│
└── README.md
```

---

#  Future Enhancements

- Customer Insights Dashboard
- Inventory Analysis
- Sales Forecasting
- Time Intelligence (MTD, QTD, YTD)
- Drill-through Pages
- Power BI Service Deployment
- Row-Level Security (RLS)

---

# Author

**Khurram**

Aspiring Data Analyst with hands-on experience in:

- Microsoft Power BI
- SQL Server
- Advanced Excel
- Power Query
- DAX

Passionate about transforming business data into actionable insights through modern Business Intelligence solutions.




