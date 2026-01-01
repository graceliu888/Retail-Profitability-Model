# Retail Profitability Model
**SKU Contribution Margin + Price Elasticity Scenario Analysis (FP&A / Revenue Analytics)**

A lightweight FP&A-style model to evaluate **SKU-level profitability** and support **pricing decisions** using contribution margin analysis and category-level elasticity assumptions.

---

## Highlights
- **SKU contribution margin** (revenue, gross profit, CM%)
- **Category-level elasticity** assumptions to estimate demand response to price changes
- **What-if scenarios** (e.g., -5%, +5%, +10%) with portfolio-level impact
- Clear, interpretable outputs suitable for FP&A / Revenue Analytics storytelling

---

## Business Questions Supported
- Which SKUs drive profit vs. just revenue?
- Will a price increase improve total profit, or will volume loss offset it?
- Which categories are more price-sensitive and should be priced differently?

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

## Getting Started
1) Install dependencies
pip install -r requirements.txt
2) Run the notebook
jupyter notebook
Open: notebooks/01_profitability_model.ipynb

---

## Model Overview

### Contribution Margin

For each SKU:

- **Revenue** = Price × Units  
- **Gross Profit** = (Price − Unit Cost) × Units  
- **CM%** = (Price − Unit Cost) / Price  

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

### SKU-level profitability
- Revenue  
- Gross profit  
- Contribution margin (%)

### Scenario comparison summary
- Total revenue  
- Total profit  
- Total units  
- Delta vs. baseline  

---

## Assumptions & Notes

- Elasticity is assigned at the **category level** for simplicity (a common approach in early-stage FP&A analysis).
- The model is designed to be **interpretable and easy to extend**, rather than statistically complex.

---

## Future Enhancements

- Estimate elasticity from historical data using regression  
- Add seasonality and promotion effects  
- Build a dbt / SQL transformation layer  
- Publish a Power BI dashboard for executive reporting  
