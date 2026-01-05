# Retail Profitability Model

SKU Contribution Margin & Price Elasticity Scenario Analysis  
*(FP&A / Revenue Analytics Project)*

---

## Overview

This project demonstrates a lightweight FP&A-style model used to evaluate **SKU-level profitability** and support **pricing decisions** through contribution margin analysis and elasticity-based scenarios.

It is designed to be simple, interpretable, and extensible — similar to internal tools used by finance and revenue analytics teams.

---

## Model Overview

### Contribution Margin

For each SKU:

- **Revenue** = Price × Units  
- **Gross Profit** = (Price − Unit Cost) × Units  
- **Contribution Margin (%)** = (Price − Unit Cost) / Price  

---

### Price Elasticity Scenario

Demand response is estimated using:

- **%ΔQ = Elasticity × %ΔP**

For a given price change:

- **New Price** = Price × (1 + %ΔP)  
- **New Units** = Units × (1 + %ΔQ)  

Revenue and profit are recomputed under each scenario.

---

## Outputs

### SKU-Level Profitability
- Revenue  
- Gross profit  
- Contribution margin (%)
- Visualizations:
  - Top SKU profitability rankings
  - Contribution margin distribution
  - Category-level summaries
  - Revenue vs. profit scatter plots

### Scenario Comparison Summary
- Total revenue  
- Total profit  
- Total units  
- Delta vs. baseline
- Visualizations:
  - Price impact on profit, revenue, and units
  - Profit change percentage analysis

### Price Sensitivity Analysis
- Optimal price point identification
- Fine-grained sensitivity curves (-20% to +25% price changes)
- Profit maximization analysis
- Category-level price sensitivity comparison  

---

## Features

- **Comprehensive Visualizations**: Multiple charts and graphs to visualize profitability and price sensitivity
- **Price Sensitivity Analysis**: Fine-grained analysis to identify optimal pricing points
- **Category-Level Analysis**: Compare price sensitivity across different product categories
- **Scenario Planning**: Test multiple price change scenarios (-10% to +15%)
- **Automated Reporting**: Generate summary reports with key insights

## Assumptions & Notes

- Elasticity is assigned at the **category level** for simplicity (a common approach in early-stage FP&A analysis).
- The model prioritizes clarity and interpretability over statistical complexity.
- Designed to be easily extended with historical data or dashboards.
- Visualizations use matplotlib and seaborn for professional presentation.

---

## Project Structure

```text
retail-profitability-model/
├── data/
│   └── sample_sales.csv
├── notebooks/
│   └── 01_profitability_model.ipynb
├── README.md
└── requirements.txt
```

## Getting Started

1. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

2. **Run the Notebook**:
   - Open `notebooks/01_profitability_model.ipynb` in Jupyter
   - Run all cells to generate the complete analysis

3. **Data Format**:
   The input CSV should have the following columns:
   - `sku`: SKU identifier
   - `category`: Product category
   - `price`: Unit price
   - `unit_cost`: Unit cost
   - `units_sold`: Units sold

## Usage

The notebook is organized into the following sections:

1. **Data Loading & Overview**: Load and explore the sales data
2. **SKU Profitability Analysis**: Calculate and visualize SKU-level metrics
3. **Price Elasticity Setup**: Configure category-level elasticity coefficients
4. **Price Scenario Analysis**: Test multiple price change scenarios
5. **Price Sensitivity Analysis**: Find optimal pricing points
6. **Category-Level Analysis**: Compare price sensitivity across categories
7. **Summary & Recommendations**: Generate final report with insights