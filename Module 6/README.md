# Module 06 - AI for Network Optimization and Management

**Course:** ITAI 4370 - AI in 5G and 6G Communications and ORAN Networks  
**Student:** Monica Joya  |  **Term:** Summer 2026

## Overview

Module 06 continued the traffic prediction work and compared several ways to forecast network load. Where Module 03 used a single Random Forest, this module put three different model families against the same data.

## Artifacts in this folder

- [`Joya_Lab04_TrafficPrediction_ITAI4370.ipynb`](Joya_Lab04_TrafficPrediction_ITAI4370.ipynb) - Builds and compares ARIMA, Linear Regression, and an LSTM on a year of hourly traffic (executed, with the RMSE comparison and forecast plots).

## Problem statement

Forecast network traffic with three different model families and compare them fairly on the same data.

## Methods and tools

Python with statsmodels (ARIMA), scikit-learn (Linear Regression), and TensorFlow/Keras (LSTM), plus pandas and Matplotlib. Error measured with RMSE.

## Results and interpretation

The Linear Regression model scored almost perfectly, which was misleading: its moving-average features in the starter code included the current hour, so each average already held the value being predicted. That is target leakage. I kept the starter code as written, changed only the one line the newer pandas version required (freq='H' to freq='h'), and documented the leakage rather than hiding it. The RMSE comparison chart is in the notebook above.

## What I learned

I learned that a near-perfect score like that is a warning sign, not a good result, and that identifying the leakage mattered more than the number. Reporting a flawed result honestly is part of doing the work right.

---
[Back to portfolio home](../README.md)
