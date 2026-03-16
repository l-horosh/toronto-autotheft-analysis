# toronto-autotheft-analysis
# Spatial & Statistical Analysis of Auto Theft Anomalies in Toronto

## Project Overview
Auto theft is a wide issue in Toronto, almost 0.5% of cars are theft. EDA revealed an anomaly: the **West Humber-Clairville** neighborhood experiences a disproportionately high volume of vehicle thefts compared to the rest of the city. 

This project moves beyond descriptive statistics to investigate the logistical drivers behind this concentration. Using geospatial data extraction and inferential statistics, this analysis tests the hypothesis that proximity to specific infrastructure (highways, industrial warehouses, and airport parking) creates a functional ecosystem facilitating organized auto theft and export.

## Tech Stack & Tools
* **Languages:** Python
* **Libraries:** Pandas, NumPy, SciPy (scipy.stats), Scikit-learn (Haversine metrics)
* **Data Retrieval:** Overpass API (OpenStreetMap)
* **Statistical Methods:** Coordinate Vectorization, Distance Matrices, t-test

## Methodology
1. **Data Ingestion & Vectorization:** Extracted historical crime data and transformed geographical coordinates (latitude/longitude) into radian-based arrays.
2. **Geospatial Feature Engineering:** Queried open-source mapping APIs to locate key infrastructural hubs across Toronto (Dealerships, Highways, Warehouses, Airport Parking, Repair Shops).
3. **Distance Matrix Calculation:** Applied the Haversine formula to compute the precise spherical distance between every theft incident and the nearest infrastructure points.
4. **Hypothesis Testing:** Applied t-test to determine if the concentration of thefts near these hubs in West Humber is statistically significant compared to the rest of Toronto.


## Key Findings & Business Insights

The statistical tests yielded clear evidence that the theft anomaly in West Humber is fundamentally tied to large-scale logistics and export, rather than local dismantling. 

* **Airport Long-Term Parking (1.5 km threshold):** * West Humber: 55.6% | Rest of Toronto: 1.7%
  * **P-value:**  ->>> 0.000
  * *Insight:* A staggering difference indicates large, unmonitored airport parking lots are heavily utilized as temporary "cooling off" storage for stolen vehicles.
* **Industrial Warehouses (3.0 km threshold):** * West Humber: 69.5% | Rest of Toronto: 36.8%
  * **P-value:** ->>> 0.000
  * *Insight:* The high proximity to industrial zones supports the theory that vehicles are moved to local warehouses for containerization prior to international export.
* **Highway Junctions (1.0 km threshold):**
  * West Humber: 55.7% | Rest of Toronto: 30.1%
  * **P-value:** 5.05e-131
  * *Insight:* Immediate access to high-speed escape routes is a statistically significant factor in this neighborhood's theft rate.
* **Debunking the "Chop Shop" Theory:**
  * Tests regarding proximity to auto repair shops (2.0 km) and car dealerships (500 m) showed either no statistical difference or a lower concentration in West Humber compared to the city average. This mathematically isolates the problem to export logistics rather than local parts stripping.

