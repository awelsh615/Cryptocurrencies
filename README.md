# Cryptocurrencies
## Purpose
The purpose of this project is to use unsupervised learning to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for a potential cryptocurrency investment.

The dataset available is not idea, and a large part of this project was cleaning and processing the data for use with `K-Means` ML algorithm.

## Resources
- Data source: crypto_data.csv (retrieved from [CryptoCompare](https://min-api.cryptocompare.com/data/all/coinlist))
- Software: Python 3.8.8, Jupyter notebook 6.4.0, Jupyter lab 3.0.16
- `pandas` library
- `scikit-learn` library
- `plotly` library
- `hvplot` library
  
## Process
This data needed to be cleaned and processed before use in the `PCA` algorithm.  The following information was removed from the original dataset:
- rows containing cryptocurrencies not being traded
- the "IsTrading" column (irrelevant to the clustering)
- any rows with null values
- any rows containing coines that are not mined
- currency names (although these were kept in a separate DataFrame for use later)

In addition, the data needed to be scaled with the `StandardScaler` and I used `get_dummies` to create variables for text features in the "Algorithm" and "ProofType" columns.

After the data was processed, I used `PCA` to reduce the data dimensions to three principal components and created an elbow curve to find the best K value for the `K-Means` algorithm.

[elbow curve](Images/elbow_curve.PNG)

Using k = 4 clusters, I categorized the currencies into four different classes, which can be visualized below:

[clustered classes](Images/clustered_classes.PNG)

The graph below, showing total coin supply vs. total coins mined would be very helpful for an investor deciding on a cryptocurrency in which to invest.

[total coins](Images/total_coins.PNG)
