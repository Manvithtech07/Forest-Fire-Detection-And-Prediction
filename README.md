# Forest Fire Detection and Prediction using Satellite Imagery in Uttarakhand (Nainital District)

**Project Status:** In Progress 

## 1. Project Overview

This project aims to build a machine learning models to **predict forest fire susceptibility** in the Nainital district of Uttarakhand, India. By analyzing satellite imagery and environmental data, we can identify which areas are most at risk, helping to create a "Fire Risk Map."

This project is being developed as part of "my M.E first semester project" under the guidance of Dr. Arockiaraj S, Associate Professor, Manipal School of Information Sciences and Dr. Shweta Vincent, Associate Professor, Manipal Institute of Technology, Manipal.

* **Notebook 01:** Data Preprocessing (Clipping, Cloud Masking)
* **Notebook 02:** Feature Engineering (NDVI, NBR, dNBR, Slope, Aspect)
* **Notebook 03:** Data Sampling (Stratified 10,000-point dataset)
* **Notebook 04:** Modeling (98.45% Accuracy) & Final Map Generation

## 2. Objectives

* To acquire and preprocess Landsat 8 satellite imagery (Pre- and Post-Fire).
* To acquire and process a **Digital Elevation Model (DEM)** for environmental data.
* To perform **Feature Engineering** by calculating:
    * Vegetation Indices: **NDVI**, **NBR**
    * Burn Index: **dNBR** (to identify *what* burned, for our training data)
    * Environmental Indices: **Elevation**, **Slope**, and **Aspect**
* To create a training dataset by sampling 10,000+ points from these data layers.
* To train a **Logistic regression**, **Random Forest**, **Support Vector Machine (SVM)** model to predict fire risk based on these features.

## 3. Dataset

* **Data Source:** USGS EarthExplorer
* **Satellite:** Landsat 8 (Collection 2, Level 2)
* **Elevation Data:** **SRTM 1 Arc-Second Global (DEM)**
* **Study Area:** Nainital District, Uttarakhand, India
* **Event:** April 2021 Forest Fires

## 4. Methodology

1.  **Data Acquisition:** Landsat 8 (Pre & Post-fire) and SRTM (DEM) data was downloaded from USGS EarthExplorer. A district shapefile was sourced for the study area.
2.  **Preprocessing:** All raster images were clipped to the Naini Tal boundary. A cloud mask was applied to all Landsat bands using the `QA_PIXEL` file to remove clouds, shadows, and snow.
3.  **Feature Engineering:** 8 core features were calculated and saved as new GeoTIFFs:
    * `ndvi_pre`, `ndvi_post`
    * `nbr_pre`, `nbr_post`
    * `dNBR` (used as the "ground truth" for training)
    * `elevation`, `slope`, `aspect`
4.  **Data Sampling:** A **stratified sample** of 10,000 points (5,000 burned, 5,000 unburned) was generated to create a balanced training dataset (`training_data.csv`).
5.  **Modeling:** A Random Forest Classifier was trained in Scikit-learn to predict the `Burned` class (1 or 0).
6.  **Deployment:** The trained model was used to predict the class of *every* pixel in the study area, generating the final burn scar map.

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

