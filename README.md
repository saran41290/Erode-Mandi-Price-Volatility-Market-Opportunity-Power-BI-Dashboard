# Erode Mandi Price Volatility & Market Opportunity Dashboard (2021–2025)

Power BI mini project analyzing Erode mandi prices, volatility, seasonal movement, and market opportunities using agricultural market data from 2021 to 2025.

---

## Project Overview

This project focuses on agricultural market data analysis using **Microsoft Excel** and **Power BI** on **Erode district mandi price data** from **2021 to 2025**. The project includes data cleaning, transformation, dimensional data modelling, DAX-based calculations, and the development of an interactive dashboard to analyze:

- commodity price trends
- price volatility
- market-level pricing patterns
- seasonal movement
- favourable selling opportunities

The final dashboard is designed to support agricultural market intelligence and help users make more informed selling decisions.

---

## Objective

The main objective of this project is to transform raw mandi price data into a decision-oriented dashboard that helps identify:

- commodity-wise price volatility
- high-price and low-price markets
- seasonal and monthly price movement
- modal price and price spread patterns across markets
- stable vs unstable markets
- better market opportunities based on price, spread, and recent movement

---

## Business Problem Statement

Agricultural commodity prices vary significantly across markets, varieties, and time periods. Farmers, traders, and market analysts often lack a simple visual system to identify:

- stable markets
- volatile commodities
- seasonal selling opportunities
- favourable selling locations

This project addresses that gap by building an interactive Power BI dashboard for Erode mandi data.

---

## Data Source

- **Source:** Open Government Data Platform India / AGMARKNET
- **Dataset Type:** Variety-wise daily market prices data for agricultural commodities
- **Timeline:** 2021–2025
- **Geographic Scope:** Erode district, Tamil Nadu
- **Domain:** Agriculture / Market Intelligence

The dataset contains mandi-level daily observations including:

- Arrival Date
- Commodity
- Commodity Code
- Variety
- Grade
- Market
- District
- State
- Min Price
- Max Price
- Modal Price

---

## Tools & Technologies Used

### Microsoft Excel
- Data cleaning
- Data transformation
- Standardizing text values
- Creating month and year columns
- Removing duplicates

### Power BI
- Data modelling
- DAX calculated columns
- DAX measures
- Time intelligence calculations
- Interactive dashboard creation
- Slicer-based filtering
- Trend and comparison analysis

### Power Query
- Data type correction
- Validation checks
- Transformation logic
- Invalid record removal

---

## Data Pre-Processing

### Cleaning & Transformation
The following preprocessing steps were performed:

1. Converted `Arrival_Date` into proper date format
2. Converted price columns into numeric format
3. Applied cleaning and trimming to text fields
4. Standardized market naming variations
5. Checked and removed duplicate records
6. Verified missing values and inconsistent text entries

### Derived Columns
Additional calculated columns were created to strengthen the analysis:

- **Year**
- **Month Name**
- **Month Number**
- **Quarter**
- **Price Spread**
- **Price Band**
- **Spread Category**

These fields were also used in slicers for interactive dashboard filtering.

### Data Validation
Validation checks were performed to ensure:

- `Min_Price <= Modal_Price <= Max_Price`

A validation process identified **13 invalid records**, which were excluded from the final analytical dataset to improve reliability.

---

## Data Model

The Power BI model follows a **star-schema-style structure**.

### Fact Table
- **Fact_Mandi_Erode**

### Dimension Tables
- **Dim_Commodity**
- **Dim_Market**
- **DateTable**

### Relationships
- `Fact_Mandi_Erode[Commodity_Code] → Dim_Commodity[Commodity_Code]`
- `Fact_Mandi_Erode[Arrival_Date] → DateTable[Date]`
- `Fact_Mandi_Erode[Market] → Dim_Market[Market]`

This model supports better filtering, aggregation, time-based analysis, and dashboard performance.

---

## DAX Measures and Calculations

Some of the important DAX measures used in this project include:

- Total Commodities
- Total Markets
- Average Modal Price
- Average Min Price
- Average Max Price
- Average Price Spread
- Highest Commodity Spread
- Most Volatile Commodity
- Most Volatile Market
- Previous Month Avg Modal Price
- Previous Year Avg Modal Price
- Month-Over-Month Change
- Year-Over-Year Change
- Highest MoM Gain
- Highest YoY Gain
- Top Opportunity Commodity
- Top Opportunity Market
- Market Opportunity Score
- Volatile Market Rank
- Volatile Commodity Rank

These measures were used for KPI cards, volatility analysis, ranking, time comparison, and opportunity detection.

---

## Dashboard Pages

## 1. Executive Overview Dashboard

This page provides a consolidated view of:

- total commodities
- total markets
- average modal price
- average price spread
- monthly price trend
- top commodities by average modal price
- top markets by average modal price

### Business Questions Answered
- What is the overall scope of the mandi dataset?
- What is the prevailing price level?
- Which commodities and markets are premium?

---

## 2. Volatility Analysis Dashboard

This page focuses on instability and spread behaviour across commodities and markets.

### Key Visuals
- Volatility KPI cards
- Top 10 volatile commodities
- Quarterly average price spread trend
- Monthly spread by commodity matrix
- Top 10 volatile markets

### Business Questions Answered
- Which commodities are the most volatile?
- Which markets are unstable?
- How does spread behave over time?

---

## 3. Market Opportunity Dashboard

This page combines price level, spread, and recent movement to identify better selling opportunities.

### Key Visuals
- Opportunity KPI cards
- Top commodities by MoM gain
- Opportunity trend for selected commodity
- Top commodities by YoY gain
- Opportunity table by market

### Business Questions Answered
- Which commodities and markets show better opportunity?
- Which commodities have strong recent momentum?
- Which markets provide stronger price realization with manageable spread?

---

## Key Findings

The major findings from the analysis are:

- The dataset covers **104 commodities** across **26 markets**
- The overall average modal price is approximately **₹4.82K**
- The average price spread is around **₹650**
- **Cashewnuts, Jasmine, and Kakada** emerge as premium commodities
- **Mylampadi, Sivagiri, and Moolanur** are premium markets in terms of average modal price
- **Dry Chillies** is identified as the most volatile commodity
- **Moolanur** is identified as the most volatile market
- Monthly trends indicate seasonal opportunity windows
- Better selling opportunities exist where:
  - modal price is strong
  - spread is manageable
  - recent movement is positive

---

## Business Value of the Project

This dashboard helps users:

- compare commodities and markets effectively
- understand volatility and pricing uncertainty
- detect seasonal trends in price movement
- identify stable and unstable markets
- evaluate better selling opportunities using multiple indicators instead of relying on price alone

---

## Repository Structure

```text
india-agricultural-market-intelligence-dashboard/
│
├── README.md
├── report/
│   └── Erode Mandi Analysis Report.docx
├── screenshots/
│   ├── executive-overview.png
│   ├── volatility-analysis.png
│   └── market-opportunity.png
├── dataset/
│   └── sample_dataset.csv
└── powerbi/
    └── mandi_dashboard.pbix
