## 1. Introduction

The **Pizza Order Analysis Dashboard** is an interactive Power BI project designed to transform pizza sales data into actionable business insights. The dashboard analyzes **revenue, order volume, product performance, pizza categories, sizes, and ordering patterns** through interactive KPIs, charts, and filters.

The project demonstrates practical skills in **data modeling, Power Query, DAX, data visualization, and business analysis**.

---

## 2. Dataset Information

The dataset consists of four interconnected tables:

| Table             | Description                                |
| ----------------- | ------------------------------------------ |
| **Orders**        | Order ID, order date, and order time       |
| **Order Details** | Order-level pizza quantities and pizza IDs |
| **Pizzas**        | Pizza size and price information           |
| **Pizza Types**   | Pizza name, category, and ingredients      |



### Data Model

```text
Orders
   │
   ▼
Order Details
   │
   ▼
Pizzas
   │
   ▼
Pizza Types
```

---

## 3. Methodology

The project followed a structured analytics workflow:

1. **Data Preparation** – Imported and validated the source data using Power Query.
2. **Data Modeling** – Established relationships between orders, order details, pizzas, and pizza types.
3. **DAX Analysis** – Created calculated measures for revenue, orders, quantity, and average metrics.
4. **Visualization** – Developed KPI cards, trend charts, category analysis, product rankings, and time-based visuals.
5. **Interactivity** – Added slicers for Month, Category, Pizza Size, and Pizza Name to enable dynamic analysis.

---

## 4. Key Calculations & KPIs

### Total Revenue

```DAX
Total Revenue =
SUMX(
    order_details,
    order_details[quantity] *
    RELATED(pizzas[price])
)
```

### Total Orders

```DAX
Total Orders =
DISTINCTCOUNT(orders[order_id])
```

### Total Pizzas Sold

```DAX
Total Pizzas Sold =
SUM(order_details[quantity])
```

### Average Order Value

```DAX
Average Order Value =
DIVIDE(
    [Total Revenue],
    [Total Orders]
)
```

### Average Pizzas per Order

```DAX
Average Pizza Order =
DIVIDE(
    [Total Pizzas Sold],
    [Total Orders]
)
```

### Dashboard KPI Snapshot

* **Total Revenue:** 817.86K
* **Total Orders:** 21K
* **Total Pizzas Sold:** 50K
* **Average Order Value:** 38.33
* **Average Pizzas per Order:** 2.32

---

## 5. Detailed Business Observations

* **Large-size pizzas** are a major contributor to overall revenue, indicating an opportunity for targeted size-upgrade offers.
* The **Classic category** demonstrates strong sales performance and represents an important category for maintaining revenue.
* Sales are concentrated among a group of **high-performing pizza types**, highlighting opportunities to prioritize popular products.
* **Lunch and evening periods** show strong ordering activity, making these periods important for promotions, staffing, and operational planning.
* Interactive filtering makes it easier to identify changes in performance across **time, category, size, and individual pizza products**.

---

## 6. Recommendations

* Promote **larger-size upgrades and bundled offers** to increase Average Order Value.
* Maintain sufficient inventory for **high-performing pizza types**.
* Use **peak ordering hours** to optimize staffing and promotional campaigns.
* Leverage strong-performing categories and products in targeted marketing campaigns.
* Review low-performing products to evaluate **pricing, menu placement, and promotional effectiveness**.
* Monitor dashboard KPIs regularly to support **data-driven operational and sales decisions**.

---

## 7. Conclusion

The Pizza Order Analysis Dashboard converts raw transactional data into a **business-focused analytical solution**. It provides a clear view of revenue, orders, product performance, category contribution, pizza sizes, and ordering patterns.

This project strengthened my practical expertise in **Power BI, Power Query, DAX, data modeling, data visualization, and business intelligence**, while demonstrating how data can be transformed into actionable insights for decision-making.

### 🛠️ Tools & Technologies

**Power BI | Power Query | DAX | Data Modeling | Data Visualization | Microsoft Excel**
