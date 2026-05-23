# US Geographic Mobility \& Income Analysis

### Identifying Counties and States with Top Sales Growth Potential

## Description

This project analyzes US Census data to provide data-driven recommendations on geographic areas with high business growth potential. By examining population mobility patterns and median income trends, it identifies counties where high-earning individuals are relocating — signaling areas of increasing economic opportunity.

The analysis focuses on people moving into a county from a different state, a trend accelerated post-COVID as high net earners relocated to medium and small-sized markets for better housing and quality of life. The results can help business development teams prioritize geographic expansion efforts.

## Key Questions Answered

* Which counties had the highest percent increase in population from another state?
* Which counties had the highest influx of high-earning people moving in from another state?
* What is the median income of people moving into US counties from another state?
* Which counties had the highest median income of people moving in from another state, relative to the county's overall median income?

## Tech Stack

* **Language:** Python
* **Environment:** Google Colab / Jupyter Notebook (Anaconda Navigator)
* **Libraries:**

  * `pandas` — data manipulation and analysis
  * `geopandas` — geospatial data and map plotting
  * `contextily` — basemap overlays (similar to Google Maps)
  * `matplotlib` — data visualization and histograms
  * `csv` — CSV file parsing

## Data Sources

All data sourced from official US Census Bureau datasets to ensure unbiased and transparent results:

* [**ACS 1-Year Estimates – Table B07011 (2023)**](https://data.census.gov/table/ACSDT1Y2023.B07011) — Median Income by Geographical Mobility
* [**ACS 1-Year Estimates – Table B07204 (2022)**](https://data.census.gov/table/ACSDT1Y2022.B07204) — Geographical Mobility by County
* [**Census Reporter – GeoJSON Files**](https://censusreporter.org) — Geographic boundary data for map plotting

## Methods

1. **Data ingestion** — CSV files parsed into lists of dictionaries, then converted to pandas DataFrames
2. **Data cleaning** — Replaced null values, symbols, and formatted all columns to numeric types
3. **Percent change calculation** — Compared median income of out-of-state movers vs. county overall median income to normalize for county size
4. **Mobility normalization** — Calculated the proportion of people moving in from out of state relative to total movers
5. **Data merging** — Inner join of income and mobility DataFrames on geographic ID for combined analysis
6. **Geospatial mapping** — Merged 2023 Census data with 2022 GeoJSON boundary files; converted to Web Mercator projection (EPSG:3857) for basemap overlays using contextily

## Sample Results

Top counties by percent change in median income (out-of-state movers vs. county median):

|County|County Median Income|Median Income (Out-of-State Movers)|% Change|
|-|-|-|-|
|Geauga County, OH|$43,254|$190,338|340%|
|Saline County, AR|$40,534|$115,745|186%|
|Walton County, GA|$36,318|$100,617|177%|

## How to Run

1. Clone this repository
2. Install required packages:

```bash
   pip install geopandas contextily matplotlib pandas
   ```

3. Download the Census data files from the links in the **Data Sources** section and place them in the project directory
4. Open `Juan\\\_Delgado\\\_Final\\\_Project\\\_Code.ipynb` in Jupyter Notebook or Google Colab
5. Run all cells in order

> \\\*\\\*Note:\\\*\\\* The notebook was developed using Google Colab and Anaconda Navigator. File upload paths may need to be adjusted depending on your environment.

## Special Credit

**Getting Started With GIS and Spatial Research: Census Data Analysis with Python**
UCLA Office of Advanced Research Computing (OARC)
Instructor: Yoh Kawano
[YouTube Tutorial](https://www.youtube.com/watch?v=QLJDp1XRjWA) | [GitHub Repository](https://github.com/yohman/getting-started-with-gis)

---

## Author

Juan Delgado — Syracuse University, IST 652 (School of Information Studies), 2024

