# LSTM for Inflation Forecasting #

This is an additional project that I performed to work on my machine learning assignment that I performed for my Master's Thesis which was related to inflation forecasting of the Finnish Economoy. In this project, I am working on using deep learning for time series forecasting.

### About the dataset ###
The dataset has been collected from the Finnish Statistical Department which collects monthly dataset of inflation starting from 1965 and that data has been used to create predictions. There are only two columns in the dataset:

1. Month -> with month and year of the data
2. CPI -> Consumer Price Index with 1965 being the year when the value was 100.

### Packages ###

Packages loaded for these analysis are as follows but not all the packages have been utilized:
- pandas
- numpy
- seaborn
- matplotlib
- sklearn
- lazypredict
- Keras
- Tensorflow

### Data Exploration
As a simple time series there isn't any data exploration performed on this dataset

The data has been split in such as way that the 12 month before a month is taken as the features and the following month is considered the target. A 3-layer LSTM is created with 50 hidden neurons using Keras library and regular adam and mse as the target.

### Two versions of predictions

#### Prediction using predicted value
In the first version of the prediction, the last 12 months of the training data are taken and used to predict the following month (January-December 2022) to predict January 2023. To predict February 2023 however, February-December 2022 which are the actual value and the prediction of January 2023 is taken to make the next prediciton. In this model, the inaccuracy of the previous prediction can result in the inaccuracy of the current predictions.

#### Prediction using actual values
While the same process was conducted for predicting January 2023. For February 2023, the actual value of January 2023 was used to predict the following month which meant that the accuracy of the model will not be based on the accuracy of the previous prediction.

### Reflection
This was a really interesting project as I was trying to add to what I had already performed with my Master's Thesis project. While prediction long term would require the first version of the prediction, if we just want to be 1-month ahead, the second version would be the better working model. However, there are some errors in the model as the predicted values have a downward trending graph so further work will be conducted to improve the model.