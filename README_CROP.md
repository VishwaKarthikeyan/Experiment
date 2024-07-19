# Introduction

(Consumer Product goods)CPG organizations in the processed food industry must monitor crop growth to plan their supply chain for production requirements. Doing a land survey for thousands of farms is both costly and time-consuming, hence, with the emergence of geo-spatial analytics, multiple use cases for crop growth, emissions, and disease tracking have emerged. Solving earth observation problems using satellites are both scalable and cost-effective. In our experience, organizations that procure large amounts of agricultural products and crops ( like corn, potato or coffee) leverage these solutions to avoid supply time shocks and achieve process efficiencies.

# Solution Overview

<p align="center">
  <img src="https://github.com/VishwaKarthikeyan/Experiment/blob/main/arch/arch_crop.png" alt="image" width="800" height="auto">
</p>

## Data Acquisition

<p align="center">
  <img src="https://github.com/VishwaKarthikeyan/Experiment/blob/main/arch/data_ac_crop.PNG" alt="image" width="800" height="auto">
</p>

**AWS Sagemaker**

To develop a model predicting Corn yield using AWS Sagemaker, you’ll use a multi-faceted approach integrating various data sources. Initially, the field boundaries for Corn cultivation in the USA are obtained from Cropscape, while yield data at the county level is sourced from the USDA. Satellite imagery, crucial for model training, is retrieved from AWS Geospatial services using Sentinel data for the specified geolocations. AWS SageMaker notebooks facilitate this process, and relevant weather information is integrated via APIs. The provided code snippet demonstrates the initialization of AWS services, including SageMaker Geospatial and S3 clients, to manage data collection and processing efficiently. Data points are filtered based on criteria like cloud cover, and Earth Observation Jobs are created to process satellite imagery for specific time ranges and events. The collected imagery is then overlaid with crop cover data to visualize and analyze Corn cultivation.

**Google Earth Engine**

To develop a model predicting Corn yield using Google Earth Engine (GEE), you start by acquiring relevant geospatial data. You gather satellite imagery, including vegetation indices like NDVI and EVI, which are crucial for assessing plant health. This imagery is filtered based on criteria such as cloud cover and specific time periods. Additionally, you obtain data on cropland cover, weather conditions, and soil metrics. The GEE platform allows you to process and analyze these datasets, creating composite images and integrating various data sources to understand factors affecting Corn yield and enhance predictive accuracy.

## Data Pre-processing

<p align="center">
  <img src="https://github.com/VishwaKarthikeyan/Experiment/blob/main/arch/hist_crop.PNG" alt="image" width="800" height="auto">
</p>

To analyze satellite images for vegetation assessment, you first compute vegetation indices such as NDVI, EVI, and MSAVI(for AWS Sagemaker Data) from the spectral bands (red, blue, green, and near-infrared). Using these indices and band data, you generate histograms of pixel values to visualize the distribution of each band. The histogram generation function requires the input image as a NumPy array and a parameter for the number of histogram bins, with a default set to 32 for granularity control. The function calculates histograms for each spectral band and vegetation index, then stacks these histograms, including data from different growth stages (planting, mid-growth, harvest), into a single composite histogram. This stacked histogram is then converted into a TensorFlow tensor for further analysis or modeling.

## Model Training

<p align="center">
  <img src="https://github.com/VishwaKarthikeyan/Experiment/blob/main/arch/model_crop.PNG" alt="image" width="800" height="auto">
</p>

After generating histogram data from satellite images, the data is formatted for model training, with additional weather features from the Daymet package integrated based on geographic coordinates and time ranges. Representative crop growth indices are computed from the satellite data and used as inputs for a CNN-LSTM network. This model, designed to predict county-level yield data, combines convolutional layers for feature extraction with LSTM layers for sequence modeling. The network processes images with dimensions of 32x13 over three time steps and employs dense layers for regression. Compiled with the Adam optimizer and mean squared error loss, the model is evaluated using metrics such as MSE, MAE, and MAPE to ensure accurate and reliable predictions.

## Tools/Models Used

**Google Earth Engine (GEE)**: Accesses and processes satellite imagery, computes vegetation indices (NDVI, EVI, MSAVI), and integrates weather data.

**AWS SageMaker**:Retrieves Sentinel-2 data, trains and deploys machine learning models, and provides a scalable environment for running the CNN-LSTM network.

**Cropscape Website**: Provides county-level crop yield data, which serves as the dependent variable for model training.

**Daymet Package**: Supplies weather features based on geographic coordinates for integration with satellite imagery.

**CNN-LSTM Network**: Combines convolutional layers for feature extraction with LSTM layers for sequence modeling, used for predicting crop yield from sequential satellite images.


# Training

## Data:

**Satellite Imagery**: Processed Sentinel-2 data and vegetation indices (NDVI, EVI, MSAVI) from Google Earth Engine and AWS SageMaker.

**Weather Data**: Integrated weather features from the Daymet package.

**Crop Yield Data**: County-level yield data from USDA, used as the target variable.

## Model:

**CNN-LSTM Network**: Combines Convolutional Neural Networks (CNN) for feature extraction with Long Short-Term Memory (LSTM) networks for sequence modeling.

## Optimizer:

**Adam Optimizer**: Used to minimize the mean squared error (MSE) loss function.

### Number of Epochs: 5000

### Dropout Rate: 0.2 

### LSTM Units: 32

### Dense Layer Units: 64

# Evaluation Metrics

<p align="center">
  <img src="https://github.com/VishwaKarthikeyan/Experiment/blob/main/arch/metrics_crop.PNG" alt="image" width="800" height="auto">
</p>




