# Module 03 - AI and Machine Learning Fundamentals for Telecom

**Course:** ITAI 4370 - AI in 5G and 6G Communications and ORAN Networks  
**Student:** Monica Joya  |  **Term:** Summer 2026  
**Module dates:** June 16 - June 22, 2026

## Overview

Module 03 introduced AI and machine learning for telecom, and it was where I wrote my first machine learning code. It covered how learning models help a network make faster decisions than fixed rules, mostly around the radio access network and Open RAN. This is where the course moved from how networks work to how AI improves them.

## Artifacts in this folder

- [`Joya_Assignment 3_ITAI 4370_06222026.pdf`](Joya_Assignment%203_ITAI%204370_06222026.pdf) - Five written questions on how AI fits into Open RAN, cited in APA.
- [`Joya_Lab03_TrafficPrediction_ITAI4370.ipynb`](Joya_Lab03_TrafficPrediction_ITAI4370.ipynb) - My first ML model: a Random Forest that predicts hourly network traffic (executed, with output).
- [`Exercise 3_1 to 3_3.pdf`](Exercise%203_1%20to%203_3.pdf) - Three short exercises: prediction, anomaly detection, and customer segmentation.
- [`Lab03 Screenshot.png`](Lab03%20Screenshot.png) - Traffic prediction output.

## Problem statement

Predict hourly network traffic from its recent history, then practice the three core machine learning jobs (prediction, anomaly detection, grouping) on telecom-shaped data.

## Methods and tools

Python with scikit-learn (RandomForestRegressor, IsolationForest, DBSCAN, KMeans, PCA), pandas, and Matplotlib. Feature engineering with lag features and rolling averages.

## Results and interpretation

The traffic model learned the daily and weekly pattern well, and feature importance showed the traffic from one hour and twenty-four hours earlier mattered most. The exercises scored anomaly detection with precision, recall, and F1 rather than plain accuracy, since the rare events are the point.

![Traffic prediction](Lab03%20Screenshot.png)

*Figure 5. Random Forest traffic prediction output.*

## What I learned

I learned that this is supervised regression, where the model learns from labeled past data to predict a number, and that a Random Forest fits it because averaging many decision trees keeps the result steady on pattern-heavy data. Across the exercises I learned the difference between the three core jobs: regression predicts a value, anomaly detection flags the unusual, and clustering groups similar records, and the last two work without labels, which fits telecom data since most of it is never labeled.

---
[Back to portfolio home](../README.md)
