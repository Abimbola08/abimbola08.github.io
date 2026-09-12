---
layout: page
title: Statewide weather-related crash risk mapping
description: Space-time cubes, EPDO risk scores, and machine learning to find and explain high-risk locations across North Carolina.
img: assets/img/projects/crash-risk-map.png
importance: 1
category: research
related_publications: ogungbire2025spatiotemporal, ogungbire2026forecasting
---

Weather-related crashes cluster in space and time, but statewide datasets are large, noisy, and heavily imbalanced. This project built an end-to-end workflow for North Carolina that aggregates crashes into a 5-mile, monthly **space-time cube**, scores each cell with an equivalent-property-damage-only (EPDO) risk measure, and trains machine learning models to identify, predict, and interpret high-risk cells.

Key pieces of the work:

- Geospatial feature engineering from crash, roadway, and weather data.
- Tree-based models (random forest, XGBoost) with model-interpretation methods to explain what drives risk in each region.
- A deep learning extension (ConvLSTM) that forecasts risk over heterogeneous spatiotemporal data, now available as a preprint.

The approach gives agencies a map of where and when weather-related risk is expected to rise, which supports proactive countermeasures such as targeted maintenance, signage, and enforcement.
