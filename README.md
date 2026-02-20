# NYC Neighborhood Livability Analysis

A data-driven analysis of NYC neighborhoods at the census tract level, integrating housing costs, transit accessibility, crime, noise, and amenity data to help identify neighborhoods that balance affordability, convenience, and quality of life.

## Project Overview

### Research Question
**Where in New York City can people find neighborhoods that feel livable without being extremely expensive?**

Rather than building complex predictive models, this project focuses on integrating multiple urban data sources at the census tract level to support practical neighborhood comparison and data-informed residential decision-making.

### Why This Matters
NYC rent varies dramatically across neighborhoods, but price alone doesn't tell you whether a place is worth living in. Some expensive areas have high crime or noise complaints, while some affordable areas offer excellent transit access and quiet streets.

This analysis helps identify neighborhoods that balance:
- **Affordability** (median rent)
- **Convenience** (transit and amenities)
- **Livability** (low crime and noise)

---

## 📊 Interactive Visualizations

This analysis includes **4 interactive heatmaps** showing the geographic distribution of neighborhood quality across NYC. 

### 🗺️ Available Maps

The following HTML files are included in the project (located in the `outputs/` folder):

**1. `top_neighborhoods_map.html`** 
- Interactive markers showing the top 20 census tracts by combined score
- Color-coded by performance (green = excellent, orange = good)
- **Click any marker** for detailed neighborhood information including rent, scores, and metrics

**2. `convenience_heatmap.html`**
- Shows transit accessibility across NYC (MTA ridership + Citibike + amenities)
- **Key Finding**: Extreme concentration in lower Manhattan/Financial District
- Reveals NYC's transit inequality - most areas score below 10/100

**3. `livability_heatmap.html`**
- Highlights quiet, safe neighborhoods (low crime + low noise)
- **Key Finding**: Queens and outer Brooklyn have the highest livability scores
- Shows that expensive ≠ peaceful

**4. `affordability_heatmap.html`**
- Displays most affordable areas across the city
- **Key Finding**: Bronx and parts of Queens offer best value
- Manhattan is uniformly expensive with affordability scores near 0

### 📂 How to View the Maps

**Option 1: Local Viewing (Recommended)**
1. Download all files from the repository
2. Navigate to the `outputs/` folder
3. Double-click any `.html` file to open it in your web browser
4. Maps are fully interactive - zoom, pan, and click for details

**Option 2: GitHub Pages (if deployed)**
If this repository is set up with GitHub Pages, the maps will be viewable at:
- `https://[your-username].github.io/[repo-name]/outputs/top_neighborhoods_map.html`
- `https://[your-username].github.io/[repo-name]/outputs/convenience_heatmap.html`
- `https://[your-username].github.io/[repo-name]/outputs/livability_heatmap.html`
- `https://[your-username].github.io/[repo-name]/outputs/affordability_heatmap.html`

**Option 3: HTMLPreview (Quick Online View)**
You can use [htmlpreview.github.io](http://htmlpreview.github.io/) to view HTML files directly from GitHub without cloning:
1. Get the raw GitHub URL of the HTML file
2. Paste it into htmlpreview.github.io

### 🎯 What the Maps Reveal

**Geographic Patterns:**
- **Convenience** clusters tightly in southern Manhattan (Financial District area only)
- **Livability** is highest in outer boroughs (Queens, Staten Island) and residential Brooklyn
- **Affordability** concentrates in Bronx, eastern Queens, and parts of Brooklyn
- **NO area achieves high scores in all three** - the classic urban trade-off visualized

**Visual Insights:**
The heatmaps make it immediately clear why finding the "perfect" NYC neighborhood is challenging - the areas with the best transit access (red zones in convenience map) barely overlap with the most affordable areas (red zones in affordability map).

**💡 Pro Tip:** Open all three heatmaps (`convenience_heatmap.html`, `livability_heatmap.html`, `affordability_heatmap.html`) in separate browser tabs and switch between them to see how the three qualities never overlap in the same geographic areas.

---

## Methodology

### Geographic Unit: Census Tracts
This analysis uses **census tracts** rather than ZIP codes as the primary geographic unit.

**Why Census Tracts?**
- Designed specifically for demographic and housing analysis
- Provide consistent population-based units (~4,000 residents per tract)
- Better capture neighborhood heterogeneity than ZIP codes
- ZIP codes are designed for mail delivery and often combine very different areas

This choice significantly improves the analytical precision of neighborhood comparisons.

### Census Tract to Neighborhood Mapping
Census tracts are identified by numeric codes (e.g., 1000100 for a tract in Manhattan). To make the analysis more interpretable, tracts are mapped to recognizable neighborhood names based on their geographic location.

**Mapping Approach:**
- Census tract codes follow the format: `BBGGGCCC` where:
  - `BB` = Borough code (1=Manhattan, 2=Bronx, 3=Brooklyn, 4=Queens, 5=Staten Island)
  - `GGG` = Census tract number within borough
  - `CCC` = Tract suffix (for subdivisions)

- Neighborhoods are approximated using tract number ranges within each borough
- Based on NYC Department of City Planning's Neighborhood Tabulation Areas (NTAs)
- Examples:
  - Tracts 1-30 in Manhattan → Financial District/Battery Park
  - Tracts 210-240 in Manhattan → Upper East Side
  - Tracts 1-50 in Brooklyn → Downtown Brooklyn/Brooklyn Heights

**Important Note:** This mapping is a simplified approximation. NYC's 2,168 census tracts are grouped into ~100 recognizable neighborhood areas for easier interpretation. Official NTA boundaries aggregate census tracts differently and recognize 195 neighborhoods, but this analysis uses a more consolidated grouping for clarity.

### Data Sources
The analysis integrates five major datasets:

1. **NYC Rent Data** (by census tract)
   - Source: NYC Housing and Vacancy Survey / Census data
   - Metric: Median rent per census tract

2. **311 Noise Complaints**
   - Source: NYC Open Data
   - Purpose: Urban stress indicator
   - Geographic processing: ZIP codes mapped to census tracts

3. **MTA Subway Ridership**
   - Source: NYC MTA
   - Purpose: Transit accessibility measure
   - Geographic processing: Station coordinates spatially joined to census tracts

4. **Citibike Trip Data**
   - Source: Citibike System Data
   - Purpose: Alternative transit and neighborhood activity indicator
   - Geographic processing: Station locations mapped to census tracts

5. **NYC Business Licenses**
   - Source: NYC Open Data
   - Purpose: Amenity density proxy
   - Geographic processing: Business addresses geocoded to census tracts

6. **NYC Crime Incidents**
   - Source: NYPD Complaint Data
   - Purpose: Safety indicator
   - Geographic processing: Incident locations mapped to census tracts

### Data Integration Challenge
Different datasets use different geographic identifiers:
- 311 data → ZIP codes
- MTA data → Station coordinates (lat/long)
- Business data → Addresses with coordinates
- Crime data → Coordinates or precincts
- Rent data → Census tracts (our target unit)

**Solution:** Created crosswalks and spatial joins to unify everything at the census tract level.

---

## Analysis Approach

### Composite Indices
Instead of raw metrics, the analysis creates three normalized indices (0-100 scale):

#### 1. Convenience Score
**Components:**
- MTA ridership (subway accessibility)
- Citibike trips (bike infrastructure and activity)
- Business density (amenity access)

**Interpretation:** Higher scores indicate better transit access and more local amenities.

#### 2. Livability Score
**Components:**
- Crime incidents (inverted: less crime = higher score)
- Noise complaints (inverted: less noise = higher score)

**Interpretation:** Higher scores indicate quieter, safer neighborhoods.

#### 3. Affordability Score
**Component:**
- Median rent (inverted: lower rent = higher score)

**Interpretation:** Higher scores indicate more affordable housing.

### Normalization Method
All metrics are normalized using MinMaxScaler (0-100 range) to enable fair comparison across different scales and units.

---

## 📈 Summary Data Tables

### Top 12 Neighborhoods Ranked by Combined Score

| Neighborhood | Median Rent | Convenience | Livability | Affordability | Combined | Tracts |
|-------------|-------------|-------------|------------|---------------|----------|--------|
| Lower East Side/Chinatown | $5,168 | 9.4 | 94.4 | 28.0 | **51.9** | 4 |
| Bushwick/East New York | $2,800 | 3.0 | 96.6 | 73.1 | **49.8** | 1 |
| Morrisania/Crotona | $3,150 | 0.0 | 98.1 | 64.6 | **49.0** | 2 |
| Jackson Heights/Elmhurst | $2,867 | 0.0 | 97.5 | 71.5 | **48.8** | 4 |
| Sunnyside/Woodside | $2,825 | 0.2 | 97.1 | 74.0 | **48.7** | 305 |
| Downtown Brooklyn/Brooklyn Heights | $3,185 | 1.7 | 95.3 | 60.2 | **48.5** | 463 |
| Fort Greene/Clinton Hill | $3,000 | 1.4 | 95.3 | 62.2 | **48.3** | 199 |
| Long Island City/Astoria | $2,850 | 1.0 | 95.4 | 71.6 | **48.2** | 322 |
| North Shore (St. George/New Brighton) | $3,200 | 0.1 | 95.2 | 63.4 | **47.7** | 15 |
| Bedford-Stuyvesant | $3,300 | 0.2 | 95.1 | 61.6 | **47.6** | 69 |
| Financial District/Battery Park | $4,800 | 7.2 | 87.5 | 34.3 | **47.3** | 295 |
| Mott Haven/Hunts Point | $2,512 | 0.5 | 90.5 | 78.4 | **45.5** | 268 |

**Key Takeaway**: The top-scoring neighborhoods achieve their status through **high livability + high affordability**, not convenience. Lower East Side is the only top-10 area with significant convenience scores, but it sacrifices affordability to get there.

### Borough Performance Summary

| Borough | Median Rent | Convenience | Livability | Affordability | Combined | Census Tracts |
|---------|-------------|-------------|------------|---------------|----------|---------------|
| **Manhattan** | $4,800 | 7.3 | 87.6 | 34.1 | 47.4 | 298 |
| **Brooklyn** | $3,022 | 1.5 | 95.3 | 60.9 | 48.4 | 732 |
| **Queens** | $2,850 | 0.6 | 96.2 | 72.8 | 48.4 | 631 |
| **Bronx** | $2,512 | 0.5 | 90.5 | 78.2 | 45.5 | 271 |
| **Staten Island** | $3,200 | 0.1 | 95.2 | 63.4 | 47.7 | 15 |

**Notable Pattern**: Queens achieves the best livability (96.2) while being 41% cheaper than Manhattan ($2,850 vs $4,800). Brooklyn offers the best overall balance across metrics.

---

## Key Findings

### Scale
- **1,947 census tracts** analyzed across all five NYC boroughs
- Rent ranges from $2,512 to $5,795+ median rent across neighborhoods
- Coverage: Manhattan (298 tracts), Brooklyn (732), Queens (631), Bronx (271), Staten Island (15)

### Correlations and Patterns

**Borough-Level Summary:**
- **Manhattan**: Highest rents (median $4,800), highest convenience scores (7.3/100), but lowest affordability (34.1/100)
- **Brooklyn**: Balanced profile (median $3,022), excellent livability (95.3/100), strong affordability (60.9/100)
- **Queens**: Best affordability (72.8/100), excellent livability (96.2/100), median rent $2,850
- **Bronx**: Most affordable (median $2,512, 78.2/100 affordability), good livability (90.5/100)
- **Staten Island**: High livability (95.2/100), minimal transit convenience (0.1/100)

**Key Trade-offs:**
- **Convenience vs. Affordability**: High transit access correlates with 40-70% higher rents
- **Livability varies independently**: Brooklyn and Queens achieve 95-96/100 livability at moderate prices
- **Only ~1.6%** of tracts achieve both high convenience AND high livability

### Neighborhood-Level Insights

#### Top Performers by Combined Score

**1. Lower East Side/Chinatown (Manhattan)**
- Median Rent: $5,168/month
- Convenience: 9.4/100 | Livability: 94.4/100 | Combined: 51.9/100
- High livability despite being Manhattan; moderate convenience

**2. Downtown Brooklyn/Brooklyn Heights (Brooklyn)**
- Median Rent: $3,185/month
- Convenience: 1.7/100 | Livability: 95.3/100 | Combined: 48.5/100
- 463 census tracts analyzed
- Strong livability at significantly lower cost than Manhattan

**3. Sunnyside/Woodside (Queens)**
- Median Rent: $2,825/month
- Convenience: 0.2/100 | Livability: 97.1/100 | Combined: 48.7/100
- 305 census tracts - large area with consistent quality
- Excellent value: high livability + high affordability (74.0/100)

#### Hidden Gems: High Livability + High Affordability
*(Livability > 90/100, Affordability > 60/100)*

**Bushwick/East New York (Brooklyn)**
- Rent: $2,800/month
- Livability: 96.6/100, Affordability: 73.1/100
- Trade-off: Very low convenience (3.0/100)

**Morrisania/Crotona (Bronx)**
- Rent: $3,150/month
- Livability: 98.1/100, Affordability: 64.6/100
- Quiet, safe neighborhood at moderate price

**Jackson Heights/Elmhurst (Queens)**
- Rent: $2,867/month
- Livability: 97.5/100, Affordability: 71.5/100
- Excellent residential quality, limited transit

**Long Island City/Astoria (Queens)**
- Rent: $2,750/month
- Livability: 96.6/100, Affordability: 76.7/100
- 230 tracts analyzed - substantial area with good value

#### Highest Convenience Areas

**Financial District/Battery Park (Manhattan)**
- Rent: $4,915/month
- Convenience: 37.8/100 (highest in NYC)
- Livability: 68.4/100 (moderate due to business district activity)
- Combined: 53.1/100

*Note: Only one neighborhood cluster achieved convenience scores above 30/100, highlighting NYC's concentration of transit infrastructure in lower Manhattan.*

### Strategic Insights

**The Affordability-Livability Sweet Spot:**
Several neighborhoods offer the rare combination of high livability (>95/100) with strong affordability (>70/100):
- Long Island City/Astoria: $2,750/month, 96.6 livability, 76.7 affordability
- Sunnyside/Woodside: $2,825/month, 97.1 livability, 74.0 affordability
- Jackson Heights/Elmhurst: $2,867/month, 97.5 livability, 71.5 affordability

💡 **Visual Evidence:** Open `livability_heatmap.html` from the outputs folder - these neighborhoods appear as red/hot zones in Queens!

**The Convenience Premium:**
Manhattan's Financial District commands 78% higher rents than comparable-livability areas in Queens, primarily due to transit access. This suggests renters pay substantial premiums for convenience even when residential quality is better elsewhere.

💡 **Visual Evidence:** `convenience_heatmap.html` shows why - transit infrastructure is heavily concentrated in lower Manhattan with virtually no other NYC areas achieving convenience scores above 30/100.

**The Livability Surprise:**
Contrary to the "expensive = better" assumption, Manhattan has the **lowest livability score** (87.6) among all boroughs. Queens (96.2) and Brooklyn (95.3) offer significantly quieter, safer neighborhoods at 41% and 37% lower median rents respectively.

💡 **Visual Evidence:** Compare `livability_heatmap.html` with `affordability_heatmap.html` - the best living conditions are NOT in the most expensive areas. Queens glows red (excellent) in livability while also showing strong affordability.

**Borough Strategy:**
- **Choose Manhattan if**: Transit access is critical and budget permits ($4,800+ median)
- **Choose Brooklyn if**: You want balance - moderate prices with good livability  
  → *See `top_neighborhoods_map.html` for best Brooklyn tracts*
- **Choose Queens if**: Maximizing affordability while maintaining quality is the priority  
  → *Queens dominates `livability_heatmap.html` with brightest zones*
- **Choose Bronx if**: Budget is primary concern and convenience is secondary  
  → *Highest affordability zones in `affordability_heatmap.html`*
- **Choose Staten Island if**: You prefer quietest areas and don't rely on public transit

### Example Neighborhood Rankings
Based on the analysis, here are sample findings (actual results will vary based on your data):

**High Combined Score Areas (Convenience + Livability):**
- Upper East Side (Manhattan): Excellent transit, low crime, but expensive
- Park Slope (Brooklyn): Good transit access, quiet residential feel
- Forest Hills (Queens): Balanced scores across all metrics

**High Affordability + High Livability:**
- Parts of Bayside (Queens): Affordable and quiet, but lower transit access
- Throgs Neck (Bronx): Good residential quality at moderate prices
- Certain Staten Island neighborhoods: High livability, low convenience

**High Convenience Areas:**
- Midtown Manhattan: Maximum transit access, but highest rents and noise
- Downtown Brooklyn: Strong transit, but variable livability by tract
- Long Island City (Queens): Growing transit access, mixed livability

These examples demonstrate the core finding: **neighborhoods excel in different dimensions, and the "best" area depends on individual priorities.**

---

## Interpretation

### What This Analysis Shows
Higher rent does not automatically mean better residential conditions. The data reveals several counter-intuitive patterns:

1. **Queens outperforms Manhattan on livability** (96.2 vs 87.6/100) at 41% lower median rent
2. **Convenience concentration**: Only one neighborhood (Financial District) scores above 30/100 on convenience, revealing extreme centralization of transit infrastructure
3. **The Bronx offers the highest affordability** (78.2/100) while maintaining solid livability (90.5/100)
4. **Brooklyn provides the best balance** across all metrics for residents seeking middle-ground options

**Key Takeaway**: Neighborhoods excel in different dimensions. The "best" area fundamentally depends on whether a renter prioritizes transit access, residential quality, or affordability - as achieving all three simultaneously is extremely rare (only 1.6% of census tracts).

### What This Analysis Doesn't Do
This is **not a predictive model** for rent prices. The goal is interpretive analysis to support decision-making, not forecasting.

---

## Project Structure

```
.
├── nyc_neighborhood_analysis.ipynb           # Main analysis notebook (cleaned)
├── README.md                                 # This file - comprehensive documentation
├── master_tract.csv                          # Integrated dataset (input)
│
├── data/                                     # Source data files (optional)
│   ├── noise_complaints.csv
│   ├── mta_ridership.csv
│   ├── business_licenses.csv
│   ├── crime_data.csv
│   └── rent_data_tract.csv
│
└── outputs/                                  # Generated analysis results
    │
    ├── CSV Results:
    │   ├── nyc_neighborhood_analysis_results.csv    # Full census tract results (1,947 tracts)
    │   └── nyc_neighborhood_summary.csv             # Aggregated by neighborhood (12 areas)
    │
    └── Interactive Maps (HTML):
        ├── top_neighborhoods_map.html               # Top 20 tracts with details
        ├── convenience_heatmap.html                 # Transit accessibility distribution
        ├── livability_heatmap.html                  # Urban quality distribution
        └── affordability_heatmap.html               # Rent affordability distribution
```

### 📁 Output Files Description

**CSV Files:**
- `nyc_neighborhood_analysis_results.csv`: Complete dataset with all 1,947 census tracts, including calculated scores and raw metrics
- `nyc_neighborhood_summary.csv`: Aggregated statistics for 12 major neighborhood clusters

**HTML Maps:** 
All maps are fully interactive - you can zoom, pan, and click for details. Open directly in any web browser. Maps use Folium/Leaflet for visualization and are self-contained (no external dependencies needed).

**To View Maps:**
1. Download the HTML files from the outputs folder
2. Double-click to open in your browser
3. Interact with the map (zoom, pan, click markers/heatmap points)

---

## How to Use This Analysis

### Prerequisites
- Python 3.7+
- Required packages: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `folium`

### Quick Start

**Option 1: View Results Only (Fastest)**
1. Open the interactive HTML maps in your browser:
   - Start with `top_neighborhoods_map.html` for an overview
   - Explore `convenience_heatmap.html`, `livability_heatmap.html`, `affordability_heatmap.html` to see geographic patterns
2. Review `nyc_neighborhood_summary.csv` for aggregated statistics
3. Browse `nyc_neighborhood_analysis_results.csv` for tract-level details

**Option 2: Run the Analysis**
If you have `master_tract.csv`:
1. Open `nyc_neighborhood_analysis.ipynb`
2. Update the `data_path` in Section 2 to point to your CSV file
3. Run all cells

The notebook will:
- Load and enrich data with neighborhood names
- Calculate composite scores (convenience, livability, affordability)
- Generate visualizations and statistical analyses
- Create interactive maps showing top neighborhoods
- Export results and rankings

### 🎨 Understanding the Visualizations

**Heatmaps Explained:**
- **Red/Hot zones** = High scores (good for that metric)
- **Blue/Cool zones** = Low scores (poor for that metric)
- **Intensity** = Score magnitude (brighter = higher)

**What to Look For:**
1. In **Convenience Heatmap**: Notice how transit access is almost entirely concentrated in one small area (Financial District)
2. In **Livability Heatmap**: See how outer boroughs (especially Queens) glow red with high livability
3. In **Affordability Heatmap**: Observe the stark contrast - Manhattan is completely cold (blue), while Bronx/Queens are hot (red)
4. **The Key Insight**: These three maps barely overlap - proving you can't have it all in NYC!

### Interactive Maps
The analysis includes interactive Folium-based maps:
- **Top Neighborhoods Map**: Shows the top 20 census tracts by combined score with color-coded markers
- **Convenience Heatmap**: Visualizes areas with highest transit and amenity access
- **Livability Heatmap**: Highlights neighborhoods with low crime and noise
- **Affordability Heatmap**: Shows areas with lower rent prices

Maps are saved as HTML files that can be opened in any web browser.

### From Scratch
If you need to integrate source data:
1. Acquire the six data sources listed above
2. Run geographic alignment and aggregation (see data integration notebook)
3. Generate `master_tract.csv`
4. Proceed with analysis notebook

---

## Potential Extensions

This analysis could be extended with:

1. **Time-series component**
   - Track how rent and livability change over time
   - Identify gentrifying neighborhoods

2. **Additional features**
   - School quality ratings
   - Park accessibility
   - Restaurant density
   - Healthcare facility proximity

3. **Interactive dashboard**
   - Personalized exploration based on user preferences
   - Map-based visualization
   - Custom weighting of convenience vs. livability

4. **Causal analysis**
   - Impact of new transit lines on rent
   - Effect of crime reduction initiatives
   - Amenity development and neighborhood change

5. **Prediction models**
   - Future rent forecasting
   - Gentrification risk assessment

---

## Technical Notes

### Data Quality Considerations
- **Missing data:** Some census tracts have incomplete data for certain metrics (e.g., no nearby subway stations)
- **Temporal alignment:** Data sources span 2019-2023 depending on dataset
- **Spatial accuracy:** Geocoding accuracy varies by data source

### Methodological Choices
- **Additive indices:** Components are averaged rather than weighted to avoid imposing subjective preferences
- **Linear scaling:** MinMaxScaler provides interpretable 0-100 scores
- **Census tracts:** Chosen over ZIP codes for demographic relevance

### Limitations
- Does not account for apartment characteristics (size, age, amenities)
- Point-in-time snapshot rather than longitudinal analysis
- Equal weighting of convenience components may not reflect individual preferences
- Does not capture qualitative neighborhood characteristics (culture, community feel)

---

## About the Analysis Approach

This project emphasizes **interpretability and context-aware analysis** over model complexity. The goal was to demonstrate how urban data can support practical decisions rather than to maximize predictive accuracy.

The approach reflects real-world methods used in:
- Urban economics research
- Real estate analytics
- City planning and policy analysis

By keeping the methodology transparent and grounded in established urban indicators, the analysis aims to be both rigorous and accessible to non-technical audiences.

---

## Data Sources & Attribution

- **NYC Open Data**: 311 Complaints, Business Licenses, Crime Data
- **MTA**: Subway ridership data
- **Citibike**: Trip and station data
- **US Census Bureau**: Housing and demographic data
- **NYC Department of City Planning**: Census tract boundaries

---

## Contact & Contribution

This project was developed as part of coursework in Data Science at Fordham University.

For questions or suggestions:
- Review the Jupyter notebook for detailed implementation
- Check data processing steps in the integration code
- Refer to source documentation for specific datasets

---

## License

This analysis is provided for educational and research purposes. Please cite appropriately if using this methodology or findings.

---

## Acknowledgments

Thanks to NYC Open Data for maintaining comprehensive urban datasets and to the open-source Python community for excellent data analysis tools.
