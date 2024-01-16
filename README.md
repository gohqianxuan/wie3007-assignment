# SEMMA (Dunnhumby - Retail Focused Customer Data)

## Overview

This project explores the use of data mining methodology, specifically SEMMA (Sample, Explore, Modify, Model and Access), to real-world retail data.

## Objectives

1. To investigate sales trends by examining product purchasing preferences.
2. To optimise promotions by analysing customer segmentation based on household demographics.
3. To analyse and forecast sales trends using customer purchasing behaviour and historical data.
4. To enhance sales strategies by developing predictive models for estimating basket sales values.

## Dataset Components

1. Transaction Table - contains all products purchased by households within the dataset
2. Household Demographic Table - provides a representation of demographic information for a portion of households
3. Product Table - contains information on each product sold such as department of product, product manufacturer and a brand identifier
   
## Key Tools

### SAS Enterprise Miner

Central to the project, SAS Enterprise Miner serves as the primary tool for executing various stages of the SEMMA methodology, with a focus on the Explore (association rule mining, sequence analysis, time series clustering) and Model (decision tree, random forest, gradient boosting) phases.

### Talend Data Preparation

Focused on ensuring data integrity, Talend Data Preparation plays a crucial role in cleaning and pre-processing the data before further analysis. It specifically addresses issues such as missing values, ensuring that the dataset is devoid of inconsistencies that could impact the quality of subsequent analyses.

### Talend Data Integration

Integral to the project's success, Talend Data Integration facilitates the seamless merging of the three essential tables—transaction, household demographic, and product—forming a unified dataset for comprehensive analysis. Beyond mere merging, it generates new columns vital for our exploration, ensuring that the integrated dataset encapsulates the necessary information for a thorough investigation.

### KNIME

KNIME contributes to the exploratory phase, providing additional capabilities for cluster analysis, particularly employing DBSCAN. Its flexibility allows for the implementation of advanced analytical techniques, complementing the capabilities of SAS Enterprise Miner and enhancing the scope of exploratory data analysis.

## Techniques Applied

### Explore

1. Association Rule Mining
2. Sequence Analysis
3. Time Series Clustering
4. DBSCAN (utilizing KNIME)

## Modeling

1. Decision Trees
2. Random Forests
3. Gradient Boosting
4. Time Series Exponential Smoothing
