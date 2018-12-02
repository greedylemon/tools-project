# tools-project

## model predictions
In this section, one could utilized the function to find the best prediction model for each stock tickets that one is interested in. 
### initializing
Import necessary libiraies:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
```
import dataset:
```
df = pd.read_csv('stock_price_list',delimiter='\t')
```
### application
Apply the function (you could find it in aggregated_prediction_models.ipynb) to stock that your are interested in:
```
best_model('AAPL')
```
sample result would be: (rms stands for mean square error)
```
linear_regression model is the best with rms: 36.249188679694555
```
and corresponding prediction graph will be shown as the result.
### model explanation
The best model selection are choosen from three separated models: k-Nearest Neighbors model, linear regression model and prediction_moving_average. Those three models are shown in detail in correspondind ipynb files. The best model is selescted based on minimum rms (mean square error). 
