# Forest Fire Detection and Prediction using Satellite Imagery in Uttarakhand (Nainital District)

**Project Status:** In Progress 

## 1. Project Overview

This project aims to build a machine learning models to **predict forest fire susceptibility** in the Nainital district of Uttarakhand, India. By analyzing satellite imagery and environmental data, we can identify which areas are most at risk, helping to create a "Fire Risk Map."

This project is being developed as part of "my M.E first semester project" under the guidance of Dr. Arockiaraj S, Associate Professor, Manipal School of Information Sciences and Dr. Shweta Vincent, Associate Professor, Manipal Institute of Technology, Manipal.

* **Notebook 01:** Data Preprocessing (Clipping, Cloud Masking)
* **Notebook 02:** Feature Engineering (NDVI, NBR, dNBR, Slope, Aspect)
* **Notebook 03:** Data Sampling (Stratified 10,000-point dataset)
* **Notebook 04:** Modeling (98.45% Accuracy) & Final Map Generation

## 2. Dataset

* **Data Source:** USGS EarthExplorer
* **Satellite:** Landsat 8 (Collection 2, Level 2)
* **Elevation Data:** **SRTM 1 Arc-Second Global (DEM)**
* **Study Area:** Nainital District, Uttarakhand, India
* **Event:** April 2021 Forest Fires

## 3. Project Workflow & Methodology

This project was built in a 4-notebook pipeline:

* **Acquire Data:** Download and organize all necessary data, including Landsat 8 (Pre- and Post-Fire) and SRTM (DEM) satellite imagery from the USGS.
* **Preprocess Geospatial Data:** Develop a data pipeline using **GeoPandas** and **Rasterio** to clip all satellite images to the Naini Tal district boundary and apply a cloud mask to remove bad pixels.
* **Perform Feature Engineering:** Calculate and create 7 key predictive features:
    * **Vegetation Indices:** `NDVI (pre/post)`, `NBR (pre/post)`
    * **Topographical Indices:** `Elevation`, `Slope`, `Aspect`
    * **Ground Truth:** `dNBR` (to identify burned vs. unburned areas for training).
* **Create a Balanced Dataset:** Implement a **stratified sampling** method to generate a balanced 10,000-point training dataset (`.csv`) from the feature maps.
* **Train and Compare ML Models:** Train and evaluate three different machine learning classifiers (**Logistic Regression**, **SVM**, and **Random Forest**) to find the most accurate model for this task.
* **Generate Final Prediction Map:** Use the best-performing model (Random Forest) to classify every pixel in the study area and generate a final, high-resolution burn scar map.

## 4. Tools and Technologies

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

## 5. How to Run This Project

*(This section will be filled in later)*

