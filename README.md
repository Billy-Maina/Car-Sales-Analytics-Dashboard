# Car Sales Analytics Dashboard

**A Complete Power BI Reporting Solution for Automotive Dealerships. An enterprise-grade analytics product built with Excel, Power Query, Data Modeling, and advanced DAX.**

<img width="895" height="499" alt="Overview Dashboard" src="https://github.com/user-attachments/assets/5c5e6d32-b3ec-41fc-adff-cd42a277bcea" />

---

## Project Description 

This project is a fully developed **end-to-end analytical reporting solution** designed for a multi-brand automotive dealership.  
Using **Excel as the data source**, **Power Query for ETL**, and **Power BI for modeling and visualization**, the dashboard delivers a unified, intelligent, and actionable view of the dealership’s sales performance.

The solution goes beyond standard reporting, it provides:

- **Executive KPIs** for revenue, average price, unit sales, and YoY comparisons.  
- **Weekly performance trends**, revealing sales momentum and seasonality.  
- **Product-level insights** by body style, color, transmission type, and brand.  
- **Dealer and regional performance mapping** for strategic market optimization.  
- **A detailed transaction-level audit dashboard**, enabling validation, compliance checks, and operations support.  

The result is a professional analytics asset that enhances decision-making across leadership, sales teams, regional managers, and operations.

---

## Problem Statement 

Automotive dealerships generate large volumes of sales data across multiple brands, regions, and product lines.  
However, leadership often faces these Business Pain Points:
- Reports scattered across multiple spreadsheets with no single source of truth.  
- Inability to monitor **real-time sales trends**, causing delayed decision-making.  
- Lack of clear visibility into **top-performing cars, colors, brands, and regions**.  
- No structured way to compare **month-to-date, year-to-date, and year-over-year** performance.  
- Limited insight into **dealer contribution**, weakening inventory and marketing planning.  
- Absence of a **drill-down mechanism** to validate individual transactions.

These gaps result in poor inventory allocation, lost sales opportunities, inefficient marketing spend, and reduced profitability — especially in competitive automotive markets.

---

## **What the Business Needed**
A central, trustworthy analytics system that would:

1. Integrate all sales data into one unified reporting model.  
2. Automatically compute mission-critical KPIs (MTD, YTD, YoY).  
3. Provide multi-level visibility — from executive overview to transactional detail.  
4. Identify sales patterns across products, colors, regions, and companies.  
5. Deliver insights that directly support pricing strategy, inventory decisions, and sales optimization.

This project fulfills that need with a **professional Power BI dashboard system** built for accuracy, scalability, and clarity.

---

###  **Analytical Objectives**
- Track **weekly sales velocity** to detect seasonality.  
- Compare **product mix performance** across body styles and brands.  
- Understand **color-based consumer preferences**.  
- Evaluate **regional sales strength** and identify growth markets.  
- Support management with insights for **inventory allocation** and **pricing strategy**.

---

## Dataset Overview:
The dashboard is built from a structured Excel dataset containing multi-brand automotive sales records. The data includes rich transactional and categorical details required for KPI calculations, segmentation, and trend analysis. All raw data was cleaned and transformed using Power Query to ensure accuracy and consistency before modeling in Power BI.

<img width="1320" height="600" alt="Data Overview" src="https://github.com/user-attachments/assets/23423ba4-8822-4b72-b4b4-9dc91a3ec327" />


### **Key Fields**
| Field | Description |
|-------|-------------|
| `Sale Date` | Date of sale (used for YTD/MTD/YoY calculations) |
| `Company` | Manufacturer/brand (e.g., Cadillac, Dodge, BMW, Toyota) |
| `Model` | Specific vehicle model |
| `Body Style` | SUV, Sedan, Hatchback, Convertible, etc. |
| `Color` | Exterior color |
| `Engine` | Engine capacity/type |
| `Transmission` | Manual / Automatic |
| `Dealer Region` | Sales region e.g., Aurora, Austin, Midwest |
| `Total Sales` | Revenue generated per unit |
| `Car_ID` | Unique transaction identifier |

---

## Workflow  

A structured, end-to-end BI development process was followed, aligned with enterprise analytics standards.

- **Step 1: Data Extraction** : Imported the Excel dataset into Power BI and validated column structures, formats, and anomalies.

- **Step 2: Data Cleaning (Power Query)** :Removed duplicates, normalized text fields (colors, body styles, companies), corrected casing and spacing, standardized date fields, and created conditional/grouping columns where required.

- **Step 3: Data Modeling** : Built a clean star schema with one fact table (Car Sales) and multiple dimensions (Date, Dealer Region, Company, Body Style/Color). Established one-to-many relationships and implemented a fully functional Date Table for time intelligence.

- **Step 4: DAX Metrics & Time Intelligence** : Developed core KPIs including YTD/MTD/PTD sales, Cars Sold metrics, Average Price measures, Weekly trend calculations, and YoY growth indicators.

- **Step 5: Visualization & Dashboard Design** : Designed an executive **Overview Dashboard**, a transactional **Details Dashboard**, and a segment-focused **Automatic Transmission Dashboard**, ensuring visual consistency, optimized layout, and user-friendly interactions.

-  **Step 6: Publishing & Sharing**
---

## Data Model

The solution uses a clean and efficient **Star Schema**, designed for high performance, accurate time intelligence, and simplified DAX calculations. The model centers on one fact table (`CarSales`) supported by multiple dimension tables (`Date`, `Company`, `DealerRegion`, `BodyStyle`, `Color`) that enable flexible slicing across product, region, and vehicle attributes. Relationships are structured as one-to-many from each dimension to the fact table, ensuring clear filter flow and strong analytical consistency. This design supports YTD/MTD/YoY calculations, accelerates report performance, and provides a scalable foundation for deeper insights.

---
## Key DAX Measures  

A core part of this project was building accurate and reliable **time-intelligence metrics** and KPI logic.  
Below are the key DAX calculations powering the dashboards.

---

### **Sales KPIs (YTD, MTD, PTYD)**

```DAX
YTD Total Sales = TOTALYTD(SUM(CarSales[Total Sales]), 'Date'[Date])

MTD Total Sales = TOTALMTD(SUM(CarSales[Total Sales]), 'Date'[Date])

PTYD Total Sales = CALCULATE([YTD Total Sales], SAMEPERIODLASTYEAR('Date'[Date]))
```
### Cars Sold KPIs
```DAX
YTD Cars Sold =TOTALYTD(COUNT(CarSales[Car_ID]), 'Date'[Date])

MTD Cars Sold =TOTALMTD(COUNT(CarSales[Car_ID]),'Date'[Date])

```

### Average Price Metrics
```DAX
YTD Average Price = DIVIDE([YTD Total Sales],[YTD Cars Sold])

MTD Average Price = DIVIDE([MTD Total Sales],[MTD Cars Sold])

```
### Year-Over-Year (YoY) Growth
```DAX
YoY Sales Growth % = DIVIDE([YTD Total Sales] - [PTYD Total Sales],[PTYD Total Sales])
```
### Weekly Trend Calculation
```DAX
Weekly Sales =SUM(CarSales[Total Sales])
```

## Dashboards & Visualizations

The reporting solution includes three professionally designed dashboards, each tailored to a specific audience and analytical purpose.

### Overview Dashboard

<img width="895" height="499" alt="Overview Dashboard" src="https://github.com/user-attachments/assets/5a7191d3-5333-4676-9726-a2aa7677d45b" />


This page enables leadership to make fast, high-impact decisions on inventory allocation, pricing, and marketing.

### Details Dashboard:
This dashboard provides full transactional visibility for every car sold — including model, body style, color, engine type, transmission, dealer region, company, date of sale, and revenue. It supports operational needs such as audits, compliance checks, transaction validation, dealer performance review, and verification of KPI calculations across the reporting model.

<img width="894" height="500" alt="Details Dashboard" src="https://github.com/user-attachments/assets/a25412b9-0ba6-486a-b63d-8728c62fe68c" />


### Auto Transmission Segment Dashboard

A focused dashboard analyzing the performance of automatic transmission vehicles, highlighting segment-level KPIs, body-style distribution, color preferences, weekly sales trends, and dealer contributions. This view supports targeted marketing, optimized regional stocking, and strategic decision-making for the automatic vehicle product line.

<img width="892" height="499" alt="Auto Cars Sales Overview" src="https://github.com/user-attachments/assets/68d93ecb-c930-49b9-babd-899339e20890" />

### Manual Transmission Segment Dashboard:
This dashboard provides an in-depth analysis of manual transmission vehicle performance, featuring segment-specific KPIs, body-style distribution, color preferences, weekly sales patterns, and dealer contribution insights. It enables more informed decisions around inventory planning, pricing, and targeted marketing for the manual vehicle segment.

<img width="894" height="498" alt="Manual Cars Sales Overview" src="https://github.com/user-attachments/assets/550782ed-dbae-4116-b180-615b7036782d" />

---
## Insights & Findings

The dashboards reveal several high-impact business insights:

### 1. Sales Performance
- YTD sales show strong growth, with noticeable weekly velocity patterns.  
- Mid-year weeks show peak demand — ideal periods for campaigns.  
- MTD performance is stable and aligned with past patterns.  

### 2. Product & Body Style Insights
- SUVs and Sedans lead in both sales volume and revenue contribution.  
- Hatchbacks maintain steady demand but lower revenue margins.  
- Body styles show clear differences in customer preference across regions.  

### 3. Color Preferences
- Pale White, Black, and Red dominate sales.  
- Less popular colors consistently underperform across all regions.  

### 4. Dealer & Regional Performance
- Regions such as Aurora, Austin, and Midwest are top contributors.  
- Certain regions show strong unit sales but weaker average pricing — indicating price sensitivity.  

### 5. Company / Brand Insights
- Brands like Dodge, Cadillac, Toyota, Chrysler, and BMW demonstrate consistent YTD performance.  
- Lower-performing brands present opportunities for targeted promotions or dealer incentives.  

### 6. Transmission Type Insight
- Automatic cars have higher average price points.  
- Demand for automatic vehicles is rising, signaling a shift in customer preference.  

---

## Recommendations

Based on the analytical findings, the following actions are recommended:

### 1. Inventory Optimization
- Increase stock for SUVs, Sedans, and top-selling colors (Pale White, Black).  
- Reduce inventory for underperforming styles and colors.  

### 2. Regional Strategy
- Allocate premium models to high-performing regions.  
- Deploy targeted promotions or discounts in weak-performing territories.  

### 3. Pricing Strategy
- Maintain competitive pricing for mid-range models.  
- Consider dynamic pricing for popular models during high-demand weeks.  
- Explore bundled offers for brands with declining performance.  

### 4. Marketing & Promotion
- Promote best-performing body styles and colors aggressively.  
- Run campaigns aligned with clear weekly demand peaks.  
- Focus marketing for automatic transmission cars — rising popularity suggests strong ROI.  

### 5. Operational Improvements
- Use the Details Dashboard for regular audits.  
- Monitor weekly velocity to adjust staffing and logistics.  
- Leverage YTD/YoY patterns to improve forecasting accuracy.  

---

## Tools & Technologies Used  

A complete BI technology stack was used to deliver a scalable, high-quality analytics solution.

### **Core Tools**
| Tool | Purpose |
|------|---------|
| **Excel** | Data source preparation and initial structure |
| **Power Query** | Cleaning, normalization, ETL transformations |
| **Power BI Desktop** | Data modeling, DAX measures, dashboard design |
| **DAX (Data Analysis Expressions)** | KPI creation and time-intelligence logic |

### **Supporting Concepts**
- Data Modeling (Star Schema)
- Time Intelligence (YTD, MTD, YoY, PTYD)
- Aggregation logic (SUM, COUNT, DIVIDE)
- Date and Calendar Tables
- Advanced visualization techniques










