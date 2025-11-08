# Scania Predictive Maintenance

This project performs an end-to-end **predictive maintenance analysis** on the Scania Air Compressor Failure dataset.  
It focuses on transforming high-frequency sensor data into interpretable patterns using **feature engineering**, **principal component analysis (PCA)**, and **association-rule mining (FP-Growth)**.  
The goal is to identify variables and combinations that contribute to component failure, supporting data-driven maintenance decisions.

---

## Overview

Predictive maintenance aims to forecast equipment failures before they occur by identifying data patterns that precede faults.  
This notebook demonstrates a full analytical workflow:

1. **Data preprocessing and aggregation**  
   - Aggregates operational and specification data from time-series to vehicle level.  
   - Handles missing values, scaling, and encoding using `scikit-learn` pipelines.

2. **Feature extraction and dimensionality reduction**  
   - Computes statistical features (mean, std, min, max, median, slope) per vehicle.  
   - Applies **PCA** to visualize variance structure and reduce dimensionality.

3. **Pattern discovery with association rules**  
   - Binarizes processed data and applies **FP-Growth** for interpretable rule mining.  
   - Highlights associations between operational behaviors and component failures.

4. **Visualization and interpretation**  
   - Explains data patterns using heatmaps, PCA plots, and rule graphs for maintenance insights.

---

## Dataset

This project uses the **Scania Air Compressor Failure dataset** available from the  
[Swedish National Data Service (SND)](https://researchdata.se/en/catalogue/dataset/2024-34).

Due to its size (~1.4 GB), the dataset is **not included in this repository**.  
You can request access and download it directly from SND.

After download, store the CSV files in a `data/` directory.

---

## Methods

| Step | Technique | Purpose |
|------|------------|----------|
| **1. Data Preprocessing** | Imputation, scaling, encoding (`ColumnTransformer`) | Clean and standardize inputs |
| **2. Feature Engineering** | Aggregation by vehicle ID (mean, std, min, max, median, slope) | Extract informative summary statistics |
| **3. Dimensionality Reduction** | PCA | Capture dominant variance directions and visualize structure |
| **4. Association-Rule Mining** | FP-Growth + filtering by lift/confidence | Discover interpretable relationships related to failure |
| **5. Visualization** | Heatmaps, bar charts, rule graphs | Interpret and communicate findings |

**Main libraries:** `pandas`, `numpy`, `scikit-learn`, `mlxtend`, `matplotlib`, `seaborn`, `networkx`

---

## Results

To illustrate the workflow and results, export the following figures from the notebook and place them in an `/images` folder.

1. **PCA Variance Plot**
   - Shows explained variance ratio for the top principal components.  
   - Demonstrates dimensionality reduction performance.  
   - Filename: `images/pca_variance.png`

<img width="613" height="391" alt="image" src="https://github.com/user-attachments/assets/42a944dd-19c2-41be-ae33-4fd593a14b71" />

2. **Top Association Rules**
   - Bar chart of top 12 rules by lift or confidence.  
   - Visually communicates discovered failure patterns.  
   - Filename: `images/fpgrowth_rules.png`

<img width="1220" height="843" alt="image" src="https://github.com/user-attachments/assets/05f53fb5-7fbf-4365-8b64-06cd6caf9f75" />


3. **Rule Network Visualization (optional)**
   - A network graph showing variable relationships in high-lift rules.  
   - Filename: `images/rule_network.png`

<img width="1990" height="1390" alt="image" src="https://github.com/user-attachments/assets/e44bcbb6-73c7-410f-a8c4-c76129acc1b6" />


These visuals show statistical rigor (PCA), interpretability (rules), and insight (relationships) — a balanced portfolio representation.

---

## Learning Outcomes

- Apply **feature engineering** and **PCA** to industrial time-series data.  
- Discover interpretable relationships using **association-rule mining**.  
- Build a reproducible, end-to-end predictive maintenance pipeline.  
- Visualize high-dimensional data in a meaningful, interpretable way.

---

*This project is part of a broader focus on predictive maintenance, anomaly detection, and interpretable AI for industrial analytics.*
