# Reproducibility Guide

This guide explains how someone can recreate (or validate) the dashboard.

## 1) Install Power BI Desktop
Download from Microsoft and install.

## 2) Get the sample dataset
Search for **"Power BI Financial Sample.xlsx"** (Microsoft sample). Save it locally.

## 3) Build the semantic model
- Import the Excel sheet (usually named `financials`)
- Confirm field types (Date as Date, numeric fields as Whole/Decimal numbers)

## 4) Create measures (DAX)

```DAX
Total Sales = SUM(financials[Sales])
Total Profit = SUM(financials[Profit])
Profit Margin % = DIVIDE([Total Profit], [Total Sales])
Total Units = SUM(financials[Units Sold])
Avg Sale Price = DIVIDE([Total Sales], [Total Units])
```

## 5) Build visuals (suggested)
- Cards: the five measures
- Line: Date (month/year) vs Total Sales
- Bar: Product vs Total Sales (Top N = 7–10)
- Slicers: Year, Segment, Country

## 6) Create a tooltip page
- New page → Page size: Tooltip
- Page information → Tooltip: On
- Add mini KPIs + tiny trend
- Assign this tooltip page to the Top Products bar chart

## 7) Polish
- Reduce gridlines in tooltip
- Use consistent spacing + alignment
- Use a coherent theme (light or dark)
