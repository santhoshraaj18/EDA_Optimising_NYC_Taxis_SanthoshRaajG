# NYC Yellow Taxi Data Analysis (2023)

This repository contains code and analysis for an Exploratory Data Analysis (EDA) project on the 2023 New York City Yellow Taxi trip data. The objective is to uncover insights from the data to help optimise taxi operations, focusing on service efficiency, revenue maximisation, and passenger experience.

The analysis covers data loading, cleaning, and exploratory analysis, including temporal, financial, and geographical trends.

## Data Requirements

This project requires the following datasets:

1.  **NYC Yellow Taxi Trip Data for 2023:** This analysis utilizes the 2023 taxi trip data, which is provided as **twelve separate Parquet files**, one for each month. You can download these datasets from the [NYC Taxi and Limousine Commission (TLC) website](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page) under the "Yellow Taxi Trip Records" section for the year 2023.
2.  **NYC Taxi Zones Shapefile:** Geographical analysis requires the `taxi_zones.shp` file and its associated files (e.g., `.dbf`, `.shx`, etc.). This shapefile is also available on the TLC website, often linked within resources related to spatial data or taxi zone maps. Look for resources mentioning "taxi zone shapefile" or similar terms. These files are typically provided within a `taxi_zones` folder, and the code expects this **folder structure to be maintained**.

## Setting up the Data Locally

The provided code snippets use **specific local file paths** to access the data files and the taxi zones shapefile.

**You will need to download the 2023 NYC Yellow Taxi data and the taxi zones shapefile separately** from the [NYC TLC website](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page) or other relevant sources linked there.

Once downloaded, you must **update the file paths within the code** to match the locations where you have saved the datasets on your local machine.

Key locations in the code where you will need to update file paths include:

* **Loading the monthly Parquet files:** Look for lines similar to `pd.read_parquet('file.parquet')` or the specific directory path used in the data loading loop. Ensure you point to the directory where you've saved the twelve monthly Parquet files.
* **Loading the combined sampled data:** If you are using the saved sampled data file, update the path for `pd.read_parquet('sampled_nyc_taxi_data.parquet')` or `pd.read_csv('sampled_nyc_taxi_data.csv')` to reflect its location on your system.
* **Loading the taxi zones shapefile:** Update the path for `gpd.read_file(...)` to point to the `taxi_zones.shp` file on your system. **Crucially, ensure the other associated shapefile components (.dbf, .shx, .prj, etc.) are located in the *same directory*** as the `.shp` file. If they are in a subfolder (like `taxi_zones/`), make sure your path reflects this structure (e.g., `gpd.read_file('taxi_zones/taxi_zones.shp')`).

**Failure to update these paths will result in file not found errors.**

Please adjust the paths in the notebooks or scripts before running the analysis.



Feel free to explore the code and adapt it for your own analysis!
