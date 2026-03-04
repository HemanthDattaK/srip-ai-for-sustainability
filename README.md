Delhi Airshed Land Use Classification
Project Overview

This project analyzes satellite images of the Delhi-NCR region to identify land-use types using ESA WorldCover data and a CNN model. The pipeline includes spatial filtering of satellite images, label generation from raster data, and training a deep learning model for classification.

Work Done
1. Spatial Visualization

Loaded the Delhi-NCR shapefile using GeoPandas.

Plotted the region using Matplotlib.

Converted the coordinate system to EPSG:32644.

Generated a 60 × 60 km spatial grid over the region.

2. Image Filtering

Read Sentinel-2 image filenames containing latitude and longitude.

Converted coordinates into spatial points.

Filtered images whose center coordinates fall inside the Delhi Airshed region.

Counted images before and after filtering.

3. Label Generation

Loaded ESA WorldCover raster (land_cover.tif).

Extracted the corresponding land-cover area for each satellite image using its center coordinate.

Assigned each image a land-cover label based on the dominant class.

Mapped ESA classes into simplified categories such as:

Vegetation

Cropland

Built-up

Water

Others

4. Dataset Preparation

Created labeled image dataset.

Performed 60/40 train-test split for model training and evaluation.

5. Model Training

Used ResNet18 CNN model for land-use classification.

Trained the model using the filtered satellite image dataset.

6. Model Evaluation

Evaluated the model using:

Accuracy

F1 Score

Generated a confusion matrix to analyze prediction results.

Tools Used

Python

GeoPandas

Rasterio

Matplotlib

PyTorch

Scikit-learn
