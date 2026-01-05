# NYC Rental Market & Neighborhood Livability Analysis

## Overview

This project analyzes the New York City rental market at the census tract level to understand how rent prices relate to neighborhood accessibility, urban stress, and affordability.

The project began with a practical question:

**Where in NYC can people find neighborhoods that feel livable without being extremely expensive?**

Rather than building a complex machine learning model, this analysis focuses on integrating multiple urban datasets to support neighborhood comparison and data-informed residential decisions.

---

## Why Census Tracts

Census tracts are used as the primary geographic unit instead of ZIP codes.

ZIP codes are designed for mail delivery and often combine heterogeneous areas, which can distort housing analysis. Census tracts are created specifically for demographic and housing research and provide more consistent units for understanding residential patterns.

An appendix comparing ZIP code-based aggregation is included to illustrate this decision.

---

## Data Sources

The analysis integrates publicly available NYC datasets, including:

- Median rent data
- NYC crime incidents  
- 311 noise complaints
- MTA transit activity
- Business location density

All datasets were cleaned and merged at the census tract level to ensure geographic consistency.

---

## Methodology

Instead of relying on black-box models, the project constructs interpretable neighborhood indicators to support comparison and interpretation.

### Neighborhood Indicators

**Accessibility Index**  
Combines transit activity, bike access, and business density to reflect daily convenience.

**Urban Quality Index**  
Captures environmental and social stress factors using crime incidents and noise complaints.

**Affordability Indicator**  
Represented by median rent values, with lower rents indicating relatively more affordable areas.

These indicators are designed to be interpretable rather than predictive.

---

## Key Findings

- Neighborhoods with higher accessibility often command rent premiums, particularly in transit-connected areas.
- Urban stress varies independently from rent levels, meaning higher rent does not always imply better residential conditions.
- Several neighborhoods offer a balance of moderate rent, reasonable accessibility, and lower urban stress, making them attractive candidates for renters prioritizing livability.

---

## Decision-Oriented Perspective

From a renter's perspective, the most interesting neighborhoods are not necessarily the cheapest or the most central, but those that balance affordability, accessibility, and residential quality.

The analysis is intended to support exploratory decision-making rather than to rank neighborhoods using a single score.

---

## Technical Approach

### Data Integration

Multiple datasets were merged at the census tract level. This required:
- Geographic crosswalks (ZIP codes → census tracts)
- Spatial joins (coordinates → census tracts)
- Data validation and cleaning

### Analysis Framework

The analysis uses correlation analysis and exploratory visualization rather than predictive modeling. This approach prioritizes interpretability and supports understanding of neighborhood trade-offs.

---

## Project Structure

```
nyc-rental-analysis/
├── nyc_complete_pipeline.ipynb    # Main analysis notebook
├── README.md                       # This file
└── data/
    └── master_tract.csv           # Integrated dataset
```

---

## Results Summary

### Correlation with Rent

| Factor | Correlation | Interpretation |
|--------|-------------|----------------|
| Accessibility Index | +0.644 | Strong rent premium for transit access |
| Crime Incidents | +0.230 | Urban core effect (density-related) |
| MTA Ridership | +0.206 | Transit access valued by renters |
| Urban Quality Index | -0.207 | Quality varies independently from price |

### Sample Neighborhoods

**High Quality + Moderate Price:**
- Census Tract 2051602 (Bronx): $3,150/mo, high quality
- Census Tract 4066404 (Queens): $2,750/mo, high quality

These neighborhoods demonstrate that affordable, livable options exist outside the most expensive areas.

---

## Potential Applications

- Rental market analysis
- Urban and housing research
- Real estate and neighborhood screening
- Policy and planning insights

---

## Limitations

- Analysis is cross-sectional (snapshot in time, no temporal trends)
- Indicators use equal weighting (could be optimized based on priorities)
- Focuses on NYC only (methodology is transferable to other cities)

---

## Future Extensions

Possible next steps include:
- Time-series analysis of rent trends
- Integration of school quality data
- Interactive dashboard for personalized exploration
- Causal analysis of transit development impacts

---

## Technical Stack

- **Python 3.8+**
- **Pandas, NumPy** - Data manipulation
- **Matplotlib, Seaborn** - Visualization
- **Scikit-learn** - Normalization
- **Folium** - Interactive maps (optional)

---

## Getting Started

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### Running the Analysis
```python
# Open the notebook
jupyter notebook nyc_complete_pipeline.ipynb

# If you have master_tract.csv, start from Part 3
# Otherwise, follow data acquisition instructions
```

---

## Notes

This project emphasizes interpretability and context-aware analysis. The goal is to demonstrate how urban data can be used to support practical decisions rather than to maximize predictive accuracy.

The approach reflects methods used in urban economics and real estate analytics research.

---

## Author

**Sff**  
Master's in Data Science, Fordham University  
Specialization: Urban Analytics & Real Estate Data

---

## Acknowledgments

Data sources: NYC Open Data, NY State Open Data, U.S. Census Bureau

Geographic boundaries: NYC Department of City Planning

---

## License

This project is for educational and portfolio purposes.

---

*Last updated: January 2026*
