# BC Primary Care Clinic Optimization Dashboard

**Live Interactive Application:** [Click here to view the live dashboard](https://pdkb24.github.io/bc-primary-care-optimization/)

## Overview
This interactive web GIS application presents the results of a spatial accessibility and risk mitigation model for British Columbia. The dashboard evaluates five proposed Primary Care Clinic locations (Location-Allocation output) against existing healthcare infrastructure, 2021 baseline drive-time coverage, and socioeconomic vulnerability hotspots. 

The goal of this project is to provide stakeholders with a data-driven storytelling tool to visualize how proposed infrastructure mitigates spatial isolation and serves high-need demographic areas.

## Key Features
* **Dynamic Site Profiling:** Clicking on a proposed clinic dynamically updates the sidebar to display site-specific demographics, including total population and seniors (65+) served.
* **Interactive Charting:** Integrates Chart.js to visualize vulnerability profiles.
  * *Doughnut Chart:* Demographic breakdown of seniors vs. general population.
  * *Bar Chart:* Compares the local deprivation score against the provincial average.
  * *Radar Chart:* A normalized, multi-variate site profile comparing Demand Volume, Socioeconomic Need, and Spatial Isolation.
* **State-Managed Dynamic Legend:** A custom Leaflet control that actively listens to the map state, building and collapsing the legend based on the user's active layers.
* **Responsive Map UX:** Features smooth `flyTo` camera animations when navigating between the provincial overview and specific site catchments.

## Technologies Used
* **Frontend:** HTML5, CSS3 (Flexbox), Vanilla JavaScript
* **Web Mapping API:** [Leaflet.js](https://leafletjs.com/)
* **Data Visualization:** [Chart.js](https://www.chartjs.org/)
* **Data Formats & Processing:** GeoJSON, optimized and simplified for web deployment using [Mapshaper](https://mapshaper.org/)

## Map Layers
* **The Model:** Proposed Clinics (2026) and Catchment Routes.
* **Infrastructure:** Existing Primary Care Facilities.
* **Baseline Coverage (2021):** Drive-time service area polygons (0 to 120+ minutes).
* **Vulnerability Hotspots:** Getis-Ord Gi* statistical hotspots mapping areas of high socioeconomic deprivation and spatial isolation (90%, 95%, and 99% confidence intervals).

## Local Development
To run this project locally:
1. Clone this repository: `git clone https://github.com/pdkb24/bc-primary-care-optimization.git`
2. Navigate into the directory.
3. Start a local web server to bypass CORS restrictions when loading local GeoJSON files. For example, using Python:
   ```bash
   python -m http.server 8000
4. Open your browser to http://localhost:8000.
