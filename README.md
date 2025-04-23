# UHI Regression – EY Open Science AI Challenge 2025

This repository contains my solution for the **2025 EY Open Science AI & Data Challenge**, which aims to predict **Urban Heat Island (UHI) Index** values using geospatial, satellite, and environmental data for New York City. The primary analysis and modeling workflow is found in the `regression.ipynb` notebook.

---

## 📌 Objective

The goal is to build a machine learning model to predict the UHI Index — a relative measure of local air temperature compared to the city average — using features such as:

- Satellite-derived Land Surface Temperature (Landsat)
- Vegetation index (Sentinel-2 NDVI)
- Building footprint density
- Weather station data (temperature, humidity, solar flux, wind)
- Latitude and longitude

The final output is a CSV file of predicted UHI values at defined coordinate points for leaderboard submission.

---

## 📁 Project Structure

```
.
├── regression.ipynb                  #  Main model training & prediction notebook
├── regression-ensemble.ipynb        #  Ensemble modeling experiments
├── Landsat_LST.ipynb                #  Extract and preprocess Land Surface Temperature
├── Sentinel2_GeoTIFF.ipynb          #  Sentinel-2 NDVI and vegetation processing
├── NY_Mesonet_Weather.xlsx          #  Weather data from NYS Mesonet
├── Building_Footprint.kml           #  NYC building footprint data
├── Training_data_uhi_index_2025.csv       #  Ground truth UHI index data
├── Submission_template_UHI2025-v2.csv     #  Output submission template
├── 2025 EY Open Science AI Data Challenge Participant Guidance.pdf  #  Official competition guidelines
└── README.md                     
```

---

##  Features Used

| Feature Source         | Description                                                  |
|------------------------|--------------------------------------------------------------|
| **Landsat**            | Surface temperature (thermal infrared band)                  |
| **Sentinel-2 NDVI**    | Vegetation coverage                                          |
| **Building footprint** | Local building density and urban structure                   |
| **Weather**            | Solar flux, wind speed/direction, humidity, temp             |
| **Coordinates**        | Latitude and longitude                                       |

---

##  Modeling Approach

- Data preprocessing and feature engineering
- Train-test split (70/30)
- Baseline models: Random Forest, XGBoost, Linear Regression, SVR
- Evaluation metrics: `R²`, `MAE`, `RMSE`
- Ensemble experiments (`regression-ensemble.ipynb`) using weighted and stacked models

---

##  Installation

1. Create a virtual environment and activate it:
```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

2. Install dependencies:
```bash
pip install pandas geopandas numpy scikit-learn xgboost rasterio shapely matplotlib seaborn openpyxl
```

---

##  Running the Project

1. Open `regression.ipynb` in Jupyter or VS Code.
2. Run all cells sequentially.
3. The notebook will generate a submission-ready CSV following the format in `Submission_template_UHI2025-v2.csv`.

---

##  Submission Format

The final CSV should have the following structure:
```csv
id,UHI_index
1,1.021
2,0.985
...
```

---

##  Insights

- Vegetation (NDVI) and solar flux are strong predictors of cooler areas.
- Dense building clusters and higher surface temperatures strongly align with heat hotspots.
- Incorporating temporal weather variation improves prediction accuracy slightly.

---

##  Acknowledgements

- [EY Open Science AI Challenge](https://www.ey.com/)
- [NASA Landsat](https://landsat.gsfc.nasa.gov/)
- [ESA Sentinel-2](https://sentinels.copernicus.eu/)
- [Cornell CUGIR Footprint Data](https://cugir.library.cornell.edu/)
- [New York State Mesonet](https://nysmesonet.org/)


