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

## Problem Statement / Business Need  

Automotive dealerships generate large volumes of sales data across multiple brands, regions, and product lines.  
However, leadership often faces these challenges:

### **Business Pain Points**
- Reports scattered across multiple spreadsheets with no single source of truth.  
- Inability to monitor **real-time sales trends**, causing delayed decision-making.  
- Lack of clear visibility into **top-performing cars, colors, brands, and regions**.  
- No structured way to compare **month-to-date, year-to-date, and year-over-year** performance.  
- Limited insight into **dealer contribution**, weakening inventory and marketing planning.  
- Absence of a **drill-down mechanism** to validate individual transactions.

These gaps result in poor inventory allocation, lost sales opportunities, inefficient marketing spend, and reduced profitability — especially in competitive automotive markets.

### **What the Business Needed**
A central, trustworthy analytics system that would:

1. Integrate all sales data into one unified reporting model.  
2. Automatically compute mission-critical KPIs (MTD, YTD, YoY).  
3. Provide multi-level visibility — from executive overview to transactional detail.  
4. Identify sales patterns across products, colors, regions, and companies.  
5. Deliver insights that directly support pricing strategy, inventory decisions, and sales optimization.

This project fulfills that need with a **professional Power BI dashboard system** built for accuracy, scalability, and clarity.

---

## Objectives  

###  **Core Project Objectives**

| Objective | Description | Business Value |
|----------|-------------|----------------|
| **Build a unified sales performance dashboard** | Consolidate all dealership sales into a single interactive reporting system | Enables quick, confident decision-making |
| **Provide accurate KPI tracking** | YTD, MTD, PTYD, YoY growth for sales, average price, and units sold | Establishes a data-driven performance culture |
| **Surface weekly sales trends** | Reveal demand cycles and operational patterns | Improves staffing, marketing, and supply planning |
| **Analyze product and color performance** | Compare body styles, colors, and transmission types | Supports inventory and pricing optimization |
| **Map dealer and region performance** | Identify high and low performing sales regions | Improves territorial planning & dealer incentives |
| **Create a detailed audit-level dashboard** | Provide every transaction with all attributes (model, color, region, company, price) | Enables compliance checks, validation, and deeper operational insights |

###  **Analytical Objectives**
- Track **weekly sales velocity** to detect seasonality.  
- Compare **product mix performance** across body styles and brands.  
- Understand **color-based consumer preferences**.  
- Evaluate **regional sales strength** and identify growth markets.  
- Support management with insights for **inventory allocation** and **pricing strategy**.

---

## Dataset Overview  

The dashboard is built using a structured Excel dataset representing multi-brand automotive dealership sales.  
The dataset contains rich transactional and categorical information required for KPI computation, segmentation, and trend analysis.

### **Source**
- **Excel Workbook** (cleaned and transformed using Power Query)  
- Raw dataset includes historical transactional car sales with detailed attributes.

### **Dataset Composition**
| Category | Description |
|---------|-------------|
| **Fact Table** | Transaction-level car sales records |
| **Rows** | Thousands of historical sales entries |
| **Columns** | 20+ fields per record |
| **Time Range** | Multiple years of sales data |

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

### **Data Quality Work**
- Duplicate removal  
- Handling missing or inconsistent categorical fields  
- Normalizing naming conventions (models, colors, body styles)  
- Date formatting aligned to Power BI Date Table  
- Ensuring referential integrity across dimensions  

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

---

## Workflow (Step-by-Step)

A full analytical lifecycle was followed — structured, repeatable, and aligned to enterprise BI standards.

### **Step 1 — Data Extraction**
- Imported the Excel dataset into Power BI.  
- Inspected column structures, consistency, and anomalies.

### **Step 2 — Data Cleaning (Power Query)**
- Removed duplicates and irrelevant rows.  
- Standardized string fields (colors, body styles, companies).  
- Resolved inconsistent casing and spacing.  
- Converted all date fields into proper `Date` types.  
- Added conditional columns where needed (e.g., grouping body styles).  

### **Step 3 — Data Modeling**
- Designed a **Star Schema** with:
  - 1 Fact Table (Car Sales)
  - 3+ Dimension Tables (Date, Dealer Region, Company, Color/Body Style)
- Established one-to-many relationships.
- Built an official **Date Table** using M or DAX.

### ** Step 4 — DAX Metrics & Time Intelligence**
Key KPIs and calculations developed:
- YTD, MTD, PTYD comparisons  
- YoY % Change  
- Cars Sold metrics (YTD, MTD)  
- Average Price measures  
- Weekly trend measures  

### **Step 5 — Visualization & Dashboard Design**
- Built two primary dashboards:
  - **Overview Dashboard** (executive view)
  - **Details Dashboard** (transaction-level view)
- Created an additional filtered **Automatic Transmission Dashboard**.

Design philosophy:
- Consistent color palette
- High clarity KPI cards
- Clean layout for readability
- Maintaining performance (optimized DAX & visuals)

### **Step 6 — Publishing & Sharing**
- Exported and published dashboards as high-resolution previews.
- Organized repository folders for professional presentation.

---

## Data Model

The solution uses a **clean Star Schema**, enabling fast performance, easy DAX writing, and accurate time intelligence.

### **Schema Overview**
| Table Type | Tables Included | Purpose |
|-----------|----------------|---------|
| **Fact Table** | `CarSales` | Stores all transactional sales information |
| **Dimension Tables** | `Date`, `Company`, `DealerRegion`, `BodyStyle`, `Color` | Provide descriptive attributes for slicing and analysis |

### **Relationships**
- `Date[Date]` ⟶ `CarSales[Sale Date]` *(one-to-many)*
- `Company[Company Name]` ⟶ `CarSales[Company]`
- `DealerRegion[Region]` ⟶ `CarSales[Dealer Region]`
- `BodyStyle[Style]` ⟶ `CarSales[Body Style]`

### **Benefits of the Model**
- Supports YTD/MTD/YoY time intelligence  
- Allows flexible slicing (by color, body style, region, company)  
- Simplifies DAX by ensuring single-direction filter flow  
- Reduces report load time through clean separation  

---


