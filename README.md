# Forest Fire Prediction and Mapping using Satellite Imagery in Uttarakhand (Nainital District)

**Project Status:** Completed (November 2025)

This project is being developed as part of "my M.E first semester project" under the guidance of Dr. Arockiaraj S, Associate Professor, Manipal School of Information Sciences and Dr. Shweta Vincent, Associate Professor, Manipal Institute of Technology, Manipal.

## 1. Project Overview

This project develops a complete geospatial machine learning pipeline to **predict forest fire susceptibility** and **map burn scars** in the Nainital district of Uttarakhand, India.


Using Landsat 8 satellite data from the April 2021 fire event, this project identifies the topographic and vegetative features that lead to fire risk. The final output is a high-resolution "Burn Scar Map" that has been scientifically validated by:
1.  Training a model on **pre-fire data only** to prevent data leakage, achieving **95% accuracy**.
2.  Using a **Land Use/Land Cover (LULC) mask** to eliminate false positives from agricultural land.

---

## 2. Final Result

This map shows the final predicted burn scars (in red) overlaid on a map of the district. The model successfully identifies fire-affected areas within forested regions (green) while correctly ignoring non-forested areas like farmland and towns (white/tan).

![Final Burn Scar Map (QGIS)](https://github.com/user-attachments/assets/5754edd1-ba53-4cda-9c9f-f9b62086da5f)

``

---

## 3. Project Notebooks

* **Notebook 01:** Data Acquisition & Preprocessing (Clipping, Cloud Masking)
* **Notebook 02:** Feature Engineering (NDVI, NBR, dNBR, Slope, Aspect)
* **Notebook 03:** Data Sampling (Stratified 10,000-point dataset)
* **Notebook 04:** Final Modeling & Prediction (95% Accuracy & LULC-Filtered Map)

---

## 4. Dataset

* **Data Source:** USGS EarthExplorer, ESA WorldCover
* **Satellite:** Landsat 8 (Collection 2, Level 2)
* **Elevation Data:** SRTM 1 Arc-Second Global (DEM)
* **Land Use Data:** ESA WorldCover 10m 2021 (LULC)
* **Study Area:** Nainital District, Uttarakhand, India
* **Event:** April 2021 Forest Fires

---

## 5. Project Workflow & Methodology

This project was built in a 4-notebook pipeline.

1.  **Acquire & Preprocess Data:** Downloaded Landsat 8 (Pre- and Post-Fire), SRTM (DEM), and ESA (LULC) data. All rasters were clipped to the Naini Tal district boundary (`geopandas`) and cloud-masked (`rasterio`).
2.  **Perform Feature Engineering:** Calculated and created 8 key feature maps:
    * **Vegetation Indices:** `NDVI (pre/post)`, `NBR (pre/post)`
    * **Topographical Indices:** `Elevation`, `Slope`, `Aspect`
    * **Ground Truth:** `dNBR` (used to create the `Burned` class for training).
3.  **Create a Balanced Dataset:** Implemented a stratified sampling method to generate a balanced 10,000-point training dataset (`.csv`) from the feature maps.
4.  **Train Predictive Models (Fixing Data Leakage):**
    * Trained and compared three classifiers: **Logistic Regression**, **SVM**, and **Random Forest**.
    * **Crucially**, to build a true predictive model, all *post-fire* features (`ndvi_post`, `nbr_post`) were **dropped** from the training data (X). This prevents data leakage and ensures the model predicts risk based only on pre-fire and static conditions.
    * The best model (Random Forest) achieved **94.9% accuracy**.
5.  **Analyze Model Results:**
    * The **Feature Importance** plot shows that pre-fire vegetation health (`nbr_pre`, `ndvi_pre`) and `slope` are the most significant predictors of fire.
    * The **Confusion Matrix** confirms high performance for both "Burned" and "Unburned" classes.
6.  **Generate Final Prediction Map (Fixing Cropland Error):**
    * Used the trained Random Forest model to generate a pixel-by-pixel *fire probability map*.
    * Applied a **post-processing LULC mask** to filter the map. This step removes all non-burnable areas (like **croplands**, **built-up areas**, and water), eliminating false positives. The result is a clean, accurate, and scientifically valid burn scar map.

---

## 6. Tools and Technologies

* **Programming Language:** Python
* **Libraries:**
    * `rasterio` / `geopandas` (for geospatial data handling)
    * `numpy` / `pandas` (for data manipulation)
    * `matplotlib` (for plotting)
    * `scikit-learn` (for machine learning)
* **Tools:**
    * Google Colab / Jupyter Notebook
    * QGIS (for visualization and validation)
    * Git & GitHub
