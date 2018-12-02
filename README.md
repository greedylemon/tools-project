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
Finally, apply the function to stock that your are interested in:
```
best_model('AAPL')
```
sample result would be:
```
linear_regression model is the best with rms: 36.249188679694555
```
