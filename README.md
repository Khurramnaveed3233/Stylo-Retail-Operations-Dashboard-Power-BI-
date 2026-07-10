# Stylo-Retail-Operations-Dashboard-PowerBI

![Power
BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Measures-blue) ![Power
Query](https://img.shields.io/badge/Power%20Query-ETL-green) ![Retail
Analytics](https://img.shields.io/badge/Domain-Retail-purple)

> **Retail Operations Dashboard built in Microsoft Power BI using a Star
> Schema data model, Power Query, and DAX to analyze retail sales, store
> performance, and product performance.**

## Project Overview

This project presents an end-to-end Retail Operations Dashboard
developed in Microsoft Power BI using a simulated retail dataset
inspired by Stylo Pakistan. It demonstrates the complete Business
Intelligence workflow including Power Query, Star Schema modeling, DAX,
KPI development, and interactive dashboards.

## Business Objectives

-   Monitor sales performance
-   Evaluate store performance
-   Analyze product performance
-   Track profitability
-   Support data-driven decisions

## Tech Stack

-   Microsoft Power BI
-   Power Query
-   DAX
-   Star Schema
-   Data Modeling

## Star Schema Data Model

`<img width="1622" height="969" alt="ChatGPT Image Jul 10, 2026, 09_37_33 AM" src="https://github.com/user-attachments/assets/1b063ea2-db0e-4a0b-86ab-fb1ac6587b7e" />`{=html}

## Dashboard Pages

### Executive Overview

`<img width="1153" height="675" alt="1" src="https://github.com/user-attachments/assets/40ce81ac-4b13-4c89-a9db-a6952b47876f" />`{=html}

KPIs: Total Sales 286M, Total Profit 132.93M, Profit Margin 47%, Total
Orders 26K, Average Order Value 10.98K, Return Rate 7%.

### Store Performance

`<img width="1136" height="629" alt="2" src="https://github.com/user-attachments/assets/69814c05-8aac-49be-8216-a829c72cfa3b" />`{=html}

KPIs: Total Stores 60, Average Sales/Store 4.76M, Average Profit/Store
2.22M, Average Rating 4.05, Total Customers 5K, Return Rate 7%.

### Product Performance

`<img width="1159" height="995" alt="3" src="https://github.com/user-attachments/assets/2cb1b9d4-b96a-4c79-8158-81d5ad89591a" />`{=html}

KPIs: Total Products 250, Total Categories 7, Average Product Sales
1.14M, Average Product Profit 531.73K, Average Selling Price 4.97K.

## Core DAX Measures

``` dax
Total Sales = SUM(FactSales[NetSales])
Total Profit = SUM(FactSales[Profit])
Total Orders = DISTINCTCOUNT(FactSales[InvoiceID])
Total Quantity = SUM(FactSales[Quantity])
Average Order Value = DIVIDE([Total Sales],[Total Orders])
Profit Margin % = DIVIDE([Total Profit],[Total Sales])
Return Orders = CALCULATE(COUNTROWS(FactSales),FactSales[Returned]="Yes")
Return Rate % = DIVIDE([Return Orders],[Total Orders])
Total Stores = DISTINCTCOUNT(DimStore[StoreID])
Avg Store Sales = DIVIDE([Total Sales],[Total Stores])
Avg Profit Store = DIVIDE([Total Profit],[Total Stores])
Average Rating = AVERAGE(FactSales[Rating])
Total Customers = DISTINCTCOUNT(FactSales[CustomerID])
Total Products = DISTINCTCOUNT(DimProduct[ProductID])
Total Categories = DISTINCTCOUNT(DimProduct[Category])
Avg Product Sales = DIVIDE([Total Sales],[Total Products])
Avg Product Profit = DIVIDE([Total Profit],[Total Products])
Average Selling Price = AVERAGE(FactSales[UnitPrice])
```

## Skills

-   Power BI
-   DAX
-   Power Query
-   Star Schema
-   KPI Development
-   Retail Analytics

## Author

**Khurram** --- Aspiring Data Analyst specializing in Power BI, SQL
Server, Excel, Power Query, and DAX.
