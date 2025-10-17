# Forest Fire Detection and Prediction using Satellite Imagery in Uttarakhand (Nainital District)

**Project Status:** In Progress 

## 1. Project Overview

This project aims to detect and predict forest fire-prone areas in the Uttarakhand region of India. By leveraging satellite remote sensing data, this analysis will help in identifying vulnerable zones, enabling better resource allocation and proactive fire management strategies.

This project is being developed as part of "my M.E first Semester project" under the guidance of Dr. Arockiaraj S, Associate Professor, Manipal School of Information Sciences and Dr. Shweta Vincent, Associate Professor, Manipal Institute of Technology, Manipal.

## 2. Objectives

* To acquire and preprocess Landsat 8 satellite imagery (Pre- and Post-Fire).
* To acquire and process a **Digital Elevation Model (DEM)** for environmental data.
* To perform **Feature Engineering** by calculating:
    * Vegetation Indices: **NDVI**, **NBR**
    * Burn Index: **dNBR** (to identify *what* burned, for our training data)
    * Environmental Indices: **Elevation**, **Slope**, and **Aspect**
* To create a training dataset by sampling 10,000+ points from these data layers.
* To train a **Logistic regression**,**Random Forest**,**Support Vector Machine (SVM)** model to predict fire risk based on these features.

## 3. Dataset

* **Data Source:** USGS EarthExplorer
* **Satellite:** Landsat 8 (Collection 2, Level 2)
* **Elevation Data:** **SRTM 1 Arc-Second Global (DEM)**
* **Study Area:** Nainital District, Uttarakhand, India
* **Event:** April 2021 Forest Fires

## 4. Methodology & Workflow

1.  **Data Preprocessing:**
    * Clip all satellite (Landsat) and DEM data to the Nainital district boundary.
    * Perform cloud masking on Landsat images using the `QA_PIXEL` band.
2.  **Feature Engineering:**
    * Calculate all 7 indices (NDVI, NBR, dNBR, Elevation, Slope, Aspect) and save them as new `.TIF` files.
3.  **Data Sampling:**
    * Generate 10,000+ random points within the study area.
    * Extract the value of all 7 features *plus* the dNBR (target) value at each point.
    * Save this as a single `dataset.csv` file.
4.  **Machine Learning:**
    * Load the CSV into `pandas`.
    * Split the data into training and testing sets.
    * Train a `Logistic regression`,`Random Forest Classifier`,`Support Vector Machine (SVM)` to predict `Burned (1)` or `Not Burned (0)`.
    * Evaluate the model's accuracy.

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
