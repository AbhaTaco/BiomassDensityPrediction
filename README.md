# BiomassDensityPrediction

This aim of this project is to predict biomass density in a given area using remote sensing satellite images. This is done by training machine learning models on existing biomass density data. We use the following datasets:
Remote Sensing Satellite Images: Sentinel, https://developers.google.com/earth-engine/datasets/catalog/sentinel 
Biomass Denisty: CEDA ESA Biomass Climate Change Initiative, https://catalogue.ceda.ac.uk/uuid/5f331c418e9f4935b8eb1b836f8a91b8
 
This code takes the coordinates of a place, lattitude and longitude pair, as input. It creates a rectangle by treating this coordinate as the upper left vertex and about two degrees high and three degrees wide. It then creates a dataframe using the data across the satellite image bands and the biomass data in that rectangular geographical area. The code to stack the satellite images and biomass density data to create a Pandas dataframe is inspired from the work by Spatial Thoughts, spatialthoughts.com/2024/02/07/agb-regression-gee/.

**CreateDataSetsProjectionStudy.ipynb**: There are multiple options to project the satellite images as well as the biomass density onto a grid. This code creates datasets by taking various combinations possible.

**AnalysisProjectionStudy.ipynb**: This code uses the datasets created by CreateDataSetsProjectionStudy.ipynb to compare the different projections and find the the combination that performs the best on a baseline model.

**coordinates.py**: Contains lists of coordinates all over the world, classified by region.

**CreateDataSetsEDAModels.ipynb**: Take a list of coordinates from coordinates.py and creates datasets for each coordinate.

**AnalysisEDAModels.ipynb**: Perform exploratory data analysis on datasets created by CreateDataSetsEDAModels.ipynb and train models on the data.

**PrintPlotEDAModels.ipynb**: Compare the performance of the models on datasets for places across the world. Identify which features of the satellite images have the strongest impact on model performance.

