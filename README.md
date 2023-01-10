# Cryptocurrencies

# Overview of the analysis:
The purpose of this project is to conduct an analysis for Accountability Accounting clients who are preparing to enter the cryptocurrency market.
This analysis consists of creating a report that includes which cryptocurrencies are in the trading market and how they can be grouped in order to create a classification system for this new investment.
For this, we use unsupervised learning.

# Results:
Part 1: Preprocessing the data for PCA  

We opened the crypto_data.csv file that was retrieved from the CryptoCompare website. Reading the file showed 6 columns and 1252 lines.  
# cryptographic paste  

We filtered the crypto_df DataFrame so that it only had lines where the cryptocurrencies that are being traded, with non-null values and where the coins were mined. The result was a table containing 532 rows.
In this step we also use the get_dummies() method to create variables for the two text features, Algorithm and ProofType, and use the StandardScaler fit_transform() function to standardize the features.

Part 2: Reducing Data Dimensions Using PCA  
We use the Principal Component Analysis (PCA) algorithm to reduce the dimensions of the DataFrame to three principal components, PC 1, PC 2, and PC 3.
#colar pca

Part 3: Clustering Cryptocurrencies Using K-means
Using the K-means algorithm, we created an elbow curve using hvPlot to find the best value for K.

# colar elbow
Then, we ran the K-means algorithm to predict the K clusters for the cryptocurrencies' data. We create a new dataframe and name this new column "class".
# colar predicted

Part 4: Viewing Cryptocurrency Results
In this last step, we use scatterplots with Plotly Express to visualize the distinct groups that correspond to the three main components we created in Part 2.
#colar ploty
So we created a table of all currently tradable cryptocurrencies using hvplot. table() function, where we arrive at a total of 532 tradable cryptocurrencies.
#colar tradabel

Finally, I created a hvplot scatterplot with x="TotalCoinsMined", y="TotalCoinSupply" and by="Class" and showed the CoinName when hovering over the data point.
#colar hvplot
All tables and graphs with commented code are available in the crypto_clustering.ipynb file.



