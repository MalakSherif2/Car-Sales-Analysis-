# 🚗 Car Sales Analytics Dashboard

An end-to-end **Data Analytics project** analyzing **400K+ vehicle transactions across the United States** to uncover insights into sales performance, pricing, vehicle characteristics, geographic trends, and seller performance.

The project follows a complete analytics workflow, starting from **raw data cleaning and quality validation in Python**, followed by **data modeling in SQL Server using a Star Schema**, and ending with an **interactive Power BI dashboard** for business-oriented analysis.

---

## 📌 Project Overview

The automotive market generates large volumes of transactional data containing information about vehicles, prices, sellers, locations, and sales dates.

The goal of this project was to transform raw and inconsistent vehicle sales data into a structured and analysis-ready dataset, then build an interactive dashboard capable of answering key business questions such as:

* Which vehicle brands generate the highest sales value?
* Which states contribute the most to overall sales?
* How does selling price compare with market reference price (MMR)?
* How does vehicle mileage affect valuation?
* Which sellers contribute the highest sales volume and selling value?
* What are the most common vehicle characteristics and preferences?

---

# 🎯 Business Objectives

The project focuses on four main analytical areas:

### 📈 Sales Performance

Analyze overall sales performance, selling value, and sales trends over time.

### 🌎 Geographic Analysis

Identify high-performing states and understand geographic sales distribution.

### 🚘 Vehicle Analytics

Analyze vehicle characteristics such as make, model, transmission, color, mileage, and pricing.

### 👤 Seller Performance

Compare sellers based on sales volume and total selling value to identify major market contributors.

---

# 🔄 End-to-End Data Analytics Workflow

```text
Raw Dataset
     │
     ▼
Python Data Cleaning & Validation
     │
     ▼
Cleaned Dataset
     │
     ▼
SQL Server
     │
     ▼
Star Schema Data Model
     │
     ▼
Power BI Data Model
     │
     ▼
Interactive Dashboard
     │
     ▼
Business Insights
```

---

# 🧹 1. Data Cleaning & Preparation — Python

The raw dataset required several data quality checks and transformations before being used for analysis.

Using **Python and Pandas**, the dataset was inspected, cleaned, validated, and prepared for the next stages of the project.

### Data Quality Checks

The cleaning process included:

* 🔎 Missing value detection and handling
* 🔁 Duplicate detection and removal
* ⚠️ Invalid value detection
* 🔄 Inconsistent value identification and correction
* 📊 Outlier detection and evaluation
* 🏷️ Categorical data standardization
* 🧩 Correction of inconsistencies between categorical fields
* ✅ Post-cleaning data validation

### Categorical Data Cleaning

Special attention was given to categorical attributes such as:

* Make
* Model
* Transmission
* Color
* State
* Other vehicle-related categories

Inconsistencies between fields were identified and corrected to ensure that the final dataset could be reliably analyzed.

### Data Preparation

After the cleaning and validation process, the dataset was prepared and exported for loading into **SQL Server**.

---

# 🗄️ 2. SQL Server & Data Modeling

After cleaning the raw data in Python, the dataset was loaded into **SQL Server** and organized into a **Star Schema** designed specifically for analytical reporting.

## ⭐ Star Schema

```text
                    ┌──────────────┐
                    │   Dim_Car    │
                    └──────┬───────┘
                           │
                           │
┌──────────────┐     ┌─────▼────────────┐     ┌────────────────┐
│  Dim_Date    │────▶│ Fact_Car_Sales  │◀────│ Dim_Location   │
└──────────────┘     └─────┬────────────┘     └────────────────┘
                           │
                           │
                    ┌──────▼───────┐
                    │  Dim_Seller  │
                    └──────────────┘
```

### Fact Table

**`Fact_Car_Sales`**

Contains the transactional sales data and measures used for analytical reporting.

### Dimension Tables

| Table          | Purpose                      |
| -------------- | ---------------------------- |
| `Dim_Car`      | Vehicle-related attributes   |
| `Dim_Date`     | Date and time-based analysis |
| `Dim_Location` | Geographic information       |
| `Dim_Seller`   | Seller-related information   |

### Data Modeling Tasks

* Designed a Star Schema for analytical reporting.
* Created separate fact and dimension tables.
* Added an `IDENTITY`-based key to `Dim_Car` to provide a surrogate identifier for the car dimension and establish its relationship with the fact table.
* Standardized state names for the Top 10 states, converting abbreviations such as `CA` into full state names such as `California`.
* Prepared the structured SQL Server model as the data source for Power BI.

---

# 📊 3. Power BI Dashboard

The cleaned and structured data was connected to **Power BI** to create an interactive analytical dashboard.

The dashboard uses a custom **dark-theme design** with organized navigation and multiple analytical pages.

## Dashboard Pages

### 1️⃣ Overview

Provides a high-level view of the dataset and overall sales performance.

Includes:

* Key Performance Indicators (KPIs)
* Total selling value
* Seller metrics
* Vehicle metrics
* Sales progression over time
* Overall market overview

---

### 2️⃣ Sales & Geography

Focuses on sales distribution across brands and US states.

Key analysis includes:

* Sales performance by state
* Top-performing states
* Brand performance
* Geographic distribution
* Sales value comparison

---

### 3️⃣ Vehicle Analytics

Provides a deeper analysis of vehicle characteristics and pricing.

Includes:

* Transmission distribution
* Color distribution
* Vehicle characteristics
* Average Selling Price
* Average MMR
* Odometer analysis
* Pricing relationships

---

### 4️⃣ Seller Insights

Analyzes seller performance and identifies major market contributors.

Includes:

* Top sellers by sales volume
* Top sellers by total selling value
* Seller performance comparison
* Seller contribution analysis

---

# 🔍 Key Insights

### 🚘 Top Brands

**Ford and Chevrolet** were among the leading brands in terms of sales volume and total selling value.

### 🌎 Top States

**Florida and California** emerged as the strongest-performing states based on total selling value.

### 💰 Selling Price vs. MMR

The analysis showed:

* **Average Selling Price: $13.31K**
* **Average MMR: $13.47K**

This comparison provides insight into how actual selling prices relate to the market reference value.

### 🛣️ Odometer & Valuation

The dashboard explores the relationship between **vehicle mileage (odometer)** and valuation, helping identify how vehicle usage relates to pricing.

### 👤 Seller Performance

Seller analysis highlights the major contributors to the marketplace by comparing sellers based on both **transaction volume and total selling value**.

---

# 🛠️ Tools & Technologies

| Technology         | Purpose                                         |
| ------------------ | ----------------------------------------------- |
| 🐍 **Python**      | Data cleaning, validation, transformation & EDA |
| 🐼 **Pandas**      | Data manipulation and cleaning                  |
| 🗄️ **SQL Server** | Data storage and analytical data modeling       |
| ⭐ **Star Schema**  | Structuring the analytical data model           |
| 📊 **Power BI**    | Data visualization and dashboard development    |
| 📐 **DAX**         | Measures and analytical calculations            |
| 📁 **CSV**         | Source and intermediate data format             |

---

# 📂 Project Structure

```text
Car-Sales-Analytics/
│
├── data/
│   ├── raw/
│   └── cleaned/
│
├── python/
│   └── data_cleaning_and_eda.ipynb
│
├── sql/
│   └── database_schema.sql
│
├── powerbi/
│   └── Car_Sales_Dashboard.pbix
│
├── screenshots/
│   ├── overview.png
│   ├── sales_geography.png
│   ├── vehicle_analytics.png
│   └── seller_insights.png
│
└── README.md
```

> File names can be adjusted to match the actual files included in the repository.

---

# 📸 Dashboard Preview

### Overview

![Overview Dashboard](screenshots/overview.png)

### Sales & Geography

![Sales & Geography Dashboard](screenshots/sales_geography.png)

### Vehicle Analytics

![Vehicle Analytics Dashboard](screenshots/vehicle_analytics.png)

### Seller Insights

![Seller Insights Dashboard](screenshots/seller_insights.png)

---

# 📈 Key Skills Demonstrated

This project demonstrates practical experience in:

* Data Cleaning
* Data Quality Validation
* Exploratory Data Analysis
* Data Transformation
* SQL Server
* Relational Data Modeling
* Star Schema Design
* Fact & Dimension Tables
* Surrogate Keys
* Power BI
* DAX
* Data Visualization
* Dashboard Design
* Business-Oriented Analysis
* Insight Generation

---

# 🚀 How to Explore the Project

### 1. Explore the Python Notebook

Review the data cleaning and validation process performed on the raw dataset.

### 2. Explore the SQL Schema

Review the Star Schema and relationships between:

```text
Fact_Car_Sales
Dim_Car
Dim_Date
Dim_Location
Dim_Seller
```

### 3. Open the Power BI Dashboard

Open the `.pbix` file using Power BI Desktop to interact with the dashboard.

---

# 💡 Future Improvements

Potential future improvements include:

* Adding more advanced time-series analysis
* Building predictive sales models
* Adding more detailed seller segmentation
* Incorporating additional market indicators
* Automating the data refresh pipeline
* Deploying the dashboard for online interactive access

---

# 👩‍💻 Author

**Malak Sherif**

Computer Science & Statistics Student
Aspiring Data Analyst

### Connect With Me

* 💼 LinkedIn: [Add LinkedIn URL]
* 💻 GitHub: [Add GitHub URL]

---

⭐ **If you found this project interesting, feel free to explore the repository and share your feedback!**

#DataAnalytics #PowerBI #SQL #Python #DataVisualization #BusinessIntelligence
