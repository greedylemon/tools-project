# tools-project

Our project idea coming from investorshub (https://investorshub.advfn.com/). The website provides investors stocks in new technology areas, such as 3D printing. We use data mining skills (beautiful soup) to get stocks from different sectors, and then we collected those stocks' historial close prices in recent years by using yahoo finance API. After data cleaning, we can start to do some following data analysis.
## Stock Reddit comments mining and analysis

### Description
In Comments mining, I used beautuful soup(bs4) and requests to first find url for each hot post about stock's topic: 3-D printing, alternative energy, biotechs and finance. Then I used praw(reddit api) and urls to get comments by recursivly analyzing tree strucutre of reddit's comments. 

In analysis, there are four main topics:
1.sentiment analysis
2.wordcloud graph
3.basic commnets'  complexity 
4.vadar model evaluation for key word,like 'stock'

### Application(text mining part)

```
import requests
from bs4 import BeautifulSoup
```

```
import praw
reddit = praw.Reddit(client_id='Ktip90HxAp6NDg',
                     client_secret='pz6kHCNhMrVfi0n9N3KIOkEXYYY',
                     user_agent= 'Comment Extraction (by /u/USERNAME)')
```
### Application(text analysis part)
topic1(sentiment analysis):
```
get_nrc_data()
emotion_analyzer(text,emotion_dict=emotion_dict)
```
topic2(wordcloud):
```
from wordcloud import WordCloud, STOPWORDS
import matplotlib.pyplot as plt
%matplotlib inline
```
topic3(complexity):
```
import nltk
from nltk import sent_tokenize,word_tokenize 
print('word_size:',int(number_chars/number_word),'\t','sent size:',int(number_word/number_sentence),'\t','complexity:',len(vocabulary)/number_word)
```
topic4(vadar model application):
```
import nltk
from vaderSentiment.vaderSentiment import SentimentIntensityAnalyzer
get_affect(texts[0],word = 'stock')
```






## Stock Visualization

### Description

Functions used to visualize different stock features (eg. time series plot, stock return plot, rate of return plot, heatmap plot). By applying different plot functions, input one stock name will output the corresponding plot for that stock.
 
### Application

time series plot
```
get_time_series_graph(stock)
```

stock return plot
```
get_stock_return_graph(stock)
```

rate of return plot
```
def get_rate_of_return_graph(stock)
```

candlestick plot
```
get_stock_candlestick_graph(stock)
```

return for a list of stock in heatmap plot
```
get_stock_heatmap()
```

Functions can be found in file  visualization_function.ipynb






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
and corresponding prediction graph will be shown as the result:

<img width="562" alt="screen shot 2018-12-02 at 4 40 02 pm" src="https://user-images.githubusercontent.com/44420593/49345600-0a48db00-f655-11e8-9b7a-9091e85bba17.png">

### model explanation
The best model are choosen from three separated models: k-Nearest Neighbors model, linear regression model and moving average model. Those three models are shown in detail in correspondind ipynb files. The best model is selescted based on minimum rms (mean square error). 
