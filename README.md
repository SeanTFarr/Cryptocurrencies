# Cryptocurrencies
<img src=Resources\Images\cryptocurrency.jpg>

# Overview

The purpose of this analysis is to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system, using a clustering algorithm. The crypto_data.csv used in this analysis was retrieved from CryptoCompare.

# Results
The process was completed in 4 stages:
1. Preprocessing the Data for Principal Component Analysis (PCA). 

     1. Read in the crypto_data.csv to a Pandas DataFrame named crypto_df.
    <img src=Resources\Images\crypto_df.jpg>

    2. Kept all the cryptocurrencies that are being traded.
    <img src=Resources\Images\trading_true.jpg>

    3. Dropped the IsTrading column and removed rows that have at least one null value.
    <img src=Resources\Images\dropna.jpg>
    
    4. Filtered the crypto_df DataFrame so it only has rows where coins have been mined.
    <img src=Resources\Images\coins_mined.jpg>

    5. Created a new DataFrame that holds only the cryptocurrency names and drop CoinNames from crypto_df 
    <img src=Resources\Images\coin_name_df.jpg>
    <img src=Resources\Images\drop_coin_name.jpg>

2. Reducing Data Dimensions Using PCA. PCA reduces the number of dimensions by transforming a large set of variables into a smaller one that contains most of the information in the original large set.

    -  Applied PCA to reduce the dimensions to three principal components and create a new DataFrame
    <img src=Resources\Images\pcs_df.jpg>

    


3. Clustering Cryptocurrencies Using K-means

    1. Used the pcs_df DataFrame to create an elbow curve using hvPlot to find the best value for K.
    <img src=Resources\Images\elbow.jpg>

    2. Used the pcs_df DataFrame to run the K-means algorithm to make predictions of the K clusters for the cryptocurrencies’ data and create a new DataFrame, with added CoinName column from coin_name_df and a new column, 'Class', that holds the predictions
    <img src=Resources\Images\clustered_df.jpg> 


4. Visualizing Cryptocurrencies Results

    1. Created a 3D scatter plot using the Plotly Express scatter_3d() function to plot the three clusters from the clustered_df DataFrame.
    <img src=Resources\Images\3d_scatter.jpg>

    2. Scaled the data and created hvplot scatter plot
    <img src=Resources\Images\hvplot.jpg>
   
