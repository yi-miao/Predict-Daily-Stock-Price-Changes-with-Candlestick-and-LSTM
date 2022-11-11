Predict Daily Stock Price Changes with Candlestick and LSTM

Predicting stock price changes is very challenging, and it is even more
challenging to predict daily price changes. AI gains great success in 
some areas like image processing and board gaming where there is either huge 
redundancy in the images plus great error tolerance of human perception
/understanding or limit number of strict rules. Predicting stock daily
changes is very different which requires a system to predict only one
number, tomorrow's price, with high accuracy.  

In this project, I tried to use lasted Machine Learning technology to
predict stock daily prices based on combined business and technical knowledge.
It is a end-to-end process including data aquisition, preprocessing, model
creation, model training and results visualization. There are many parameters 
tunable but I focused on the concepts and process.

System Environment
1. CPU only
2. MS Windows 11
3. Python 3.9.7
4. Tensorflow 2.8.0
5. Jupyter Notebook

Major Process Steps and Comments  
Step 1 - Download whole history of a stock as dataset base [Ref 1]  
Step 2 - Merge the base with most recent data, and serialise it  
Step 3 - Extract features (X), and calculate stock price changes (Y) [Ref 2]  
The importance of daily prices in order  
- Close  
- Open  
- High, Low  

Candlestick body and wicks (modified)
- Close-to-Open  
- Close-to-Low  
- Close-to-High
- Close-to-Close (Backward)  
- Close Price Change (Forward)  

Step 4 - Visualize most recent stock daily changes [Ref 3]  
Step 5 - Create datasets for training and testing [Ref 4]  
Step 6 - Create Keras-LSTM Model [Ref 5][Ref 6]  
- g, no. of FFNNs in a unit (RNN has 1, GRU has 3, LSTM has 4)  
- h, size of hidden units  
- i, dimension/size of input  
- num_params = g × [h(h+i) + h]  
     = 4 x [2*(2+4) + 2]  
     = 4 x [12 + 2]  
     = 56 (LSTM Layer)  

Step 7 - Train LSTM Model  
Step 8 - Visualize training loss and validation loss  
Step 9 - Visualize predicted and actual stock daily price changes  


[Ref 1] https://pypi.org/project/yfinance/  
[Ref 2] https://www.investopedia.com/articles/active-trading/092315/5-most-powerful-candlestick-patterns.asp  
[Ref 3] https://queirozf.com/entries/add-labels-and-text-to-matplotlib-plots-annotation-examples  
[Ref 4] https://machinelearningmastery.com/time-series-prediction-lstm-recurrent-neural-networks-python-keras/  
[Ref 5] http://colah.github.io/posts/2015-08-Understanding-LSTMs/  
[Ref 6] https://towardsdatascience.com/counting-no-of-parameters-in-deep-learning-models-by-hand-8f1716241889  
