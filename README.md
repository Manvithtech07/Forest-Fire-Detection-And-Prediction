# Forest Fire Detection and Prediction using Satellite Imagery in Uttarakhand (Nainital Town)

**Project Status:** In Progress 

## 1. Project Overview

This project aims to detect and predict forest fire-prone areas in the Uttarakhand region of India. By leveraging satellite remote sensing data, this analysis will help in identifying vulnerable zones, enabling better resource allocation and proactive fire management strategies.

This project is being developed as part of "my M.E first Semester project" under the guidance of Dr. Arockiaraj S, Associate Professor, Manipal School of Information Sciences and Dr. Shweta Vincent, Associate Professor, Manipal Institute of Technology, Manipal.

## 2. Objectives

* To acquire and preprocess Landsat 8/9 satellite imagery for the study area (Uttarakhand).
* To calculate key spectral indices related to vegetation health and fire, such as **NBR** (Normalized Burn Ratio) and **dNBR** (delta Normalized Burn Ratio).
* To identify areas that have been recently burned.
* (Future Goal) To build a machine learning model to predict fire risk using various geospatial factors (e.g., land cover, slope, weather data).

## 3. Dataset

* **Data Source:** USGS EarthExplorer
* **Satellite:** Landsat 8/9 (OLI/TIRS)
* **Study Area:** Uttarakhand, India
* **Data Period:** April-May 2021 Forest Fires in Uttarakhand, India

## 4. Methodology

1.  **Data Acquisition:** Download Landsat images for the study area.
2.  **Preprocessing:**
    * Cloud Masking
    * Atmospheric Correction (if needed)
    * Clipping the images to the boundary of Uttarakhand.
3.  **Feature Extraction:** Calculate spectral indices (NBR, dNBR, NDVI) and Environmental indices (Elevation,Slope,Ascept).
4.  **Analysis:** Identifying burned areas using thresholding on dNBR values.
5.  **Modeling :** Using a model (e.g., Logistic Regression, Random Forest, SVM) to predict fire probability.

## 5. Tools and Technologies

* **Programming Language:** Python
* **Libraries:**
    * `rasterio` / `geopandas` (for geospatial data handling)
    * `numpy` (for numerical operations)
    * `matplotlib` / `seaborn` (for plotting)
    * `scikit-learn` (for machine learning)
* **Tools:**
    * Google Colab / Jupyter Notebook
    * QGIS and ArcGIS (for visualization)
    * Git & GitHub

## 6. How to Run This Project

*(This section will be filled in later)*

1.  Clone the repository: `git clone https://github.com/Your-Username/Forest-Fire-Detection.git`
2.  Install the required libraries: `pip install -r requirements.txt`
3.  Run the main analysis notebook: `notebooks/01-Data-Preprocessing.ipynb`
