# Executive Sales Performance Dashboard (Power BI)

A dynamic, executive-ready Power BI dashboard designed to transform raw transactional data into actionable corporate sales insights. This project showcases advanced data modeling, DAX time-intelligence calculations, and strict adherence to modern UI/UX data design principles.

## 📊 Live Dashboard Preview
<img width="1389" height="870" alt="image" src="https://github.com/user-attachments/assets/c2c2b6a1-ef35-438a-8f04-21fce1875a23" />


---

## 🎯 Business Objective
The goal of this project was to upgrade a legacy, unpolished sales report into a highly scannable, interactive tracking tool for executives. The dashboard provides immediate clarity on revenue performance, sales volume trends, regional market success, and top-tier product/customer acquisitions.


---

## 🛠️ Tech Stack & Skills Showcased
* **Business Intelligence:** Power BI Desktop
* **Data Modeling:** Star Schema architecture (Fact and Dimension tables)
* **Calculations:** Advanced DAX (Time Intelligence, Period-over-Period context)
* **UI/UX Design:** Container-based layouts, custom dynamic color gradients, and KPI conditional formatting.


---

## 🗂️ Data Model Structure
The project utilizes a clean **Star Schema** to ensure optimal performance and seamless cross-filtering interactions across all visuals:

* **Fact Table:** `sales transactions` (Revenue, Quantities, Margin data)
* **Dimension Tables:** * `sales date` (Dedicated time-intelligence calendar table)
  * `sales customers` (Client segmentation codes and profiles)
  * `sales markets` (Geographical zones and cities)
  * `sales products` (Product inventory codes and types)

---

## 🧪 Key DAX Formulas Implemented

### 1. Same Period Last Year (Revenue LY)
Shifts the context of the total revenue measure exactly one year back to allow accurate temporal comparisons.
```dax
Revenue LY = 
CALCULATE(
    [Revenue], 
    SAMEPERIODLASTYEAR('sales date'[date])
)
```

### 2. Year-over-Year (YoY) Growth %
Calculates the definitive variance metric between current performance and past performance.
```
Revenue YoY Growth % = 
VAR __CurrentRevenue = [Revenue]
VAR __PastRevenue = [Revenue LY]
RETURN
    DIVIDE(
        __CurrentRevenue - __PastRevenue, 
        __PastRevenue, 
        0
    )
```

---

## 📈 Key Dashboard Features Built
* **Period-over-Period KPI Cards:** Displays core metrics alongside dynamic indicator strings (▲ / ▼) that automatically color-code to Green for positive growth or Red for negative drops using customized conditional formatting rules.

* **Space-Saving Slicer Navigation**: Replaced heavy tile buttons with space-efficient dropdown filters for Years and Months, keeping premium dashboard real estate focused on analytical charts.

* **Dynamic Color Scaling**: Implemented single-hue data gradients on the regional market charts to instantly guide the user's eye to high-performing territories without visual clutter.

* **App-Style Reset Functionality**: Embedded a localized user control action to rapidly wipe active filter criteria and restore default aggregate report visibility in one click.

* **Clean Data Hierarchy**: Resolved broken string truncations, normalized display unit scales (Thousands vs Millions), and explicitly filtered out null/blank pipeline records to preserve dashboard reporting integrity.

---

## 💡 Core Insights Uncovered
* **Market Dominance**: Delhi NCR stands as the runaway primary revenue driver, contributing over ₹ 220M to total sales.

* **Product Performance**: Product line Prod040 is the corporate bestseller by a massive margin, pulling in over ₹ 13.4M individually.

* **Client Portfolio Concentration**: Electricalsara Stores is the organization's highest-value relationship, making up a significant portion of overall accounts.
