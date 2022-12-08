# Cryptocurrencies

This project will work wth cryptocurrency data to fit machine learning models. Due to the absense of known outputs, we must opt for Unsupervised machine Learning technique.  
We will use clustering algorithm to group the cryptocurrencies and use visualizations to showcase our findings.

You can find the code for this project here [crypto_clustering.ipynb](https://github.com/SoumyaAbraham/Cryptocurrencies/blob/main/crypto_clustering.ipynb)  
The csv file used for this project can be found here [crypto_datya.csv](https://github.com/SoumyaAbraham/Cryptocurrencies/blob/main/crypto_data.csv)

### DELIVERABLE 1

Preprocessing the Data for PCA: In this initial step, we're getting our data ready for use. This includes:  

  * Loading the .csv file
  * Removing relevent rows and columns
  * Dropping all NAN rows and columns
  * Use *get_dummies()* to create variables for text features
  * Standardizing the data with *StandardScalar()*
  
Here is what the end product looks like:
  
![del1](https://github.com/SoumyaAbraham/Cryptocurrencies/blob/main/Images/Del1.PNG)
  
### DELIVERABLE 2
  
Using Principal Component Analysis (PCA), we will reduce the dimensions of the *x* DatFrame to three principal components, placing them in a new DataFrame.

![del2](https://github.com/SoumyaAbraham/Cryptocurrencies/blob/main/Images/Del2.PNG)

### DELIVERABLE 3

In this step, we will create an elbow curve to find the best *k*-value from the DataFrame created earlier. 

  * Reduce the previous DataFrame to three dimensions.
  * Create elbow curve using *hvPlot* to find best *k*-value
  
  ![elbow_curve](https://github.com/SoumyaAbraham/Cryptocurrencies/blob/main/Images/Del3_ElbowCurve.PNG)
  
  * Run the *K*-means algorithm to make predictions for the K clusters for the cryptocurrencies data
  * Concatenate the crypto_df and pcs_df on the same columns, using index from crypto_df
  * Add *CoinName* column 
  * Add *class* that holds the predictions (model.lables_)
  
This is what the final DataFrame will look like:
  
![clustered_df](https://github.com/SoumyaAbraham/Cryptocurrencies/blob/main/Images/Del3_final.PNG)
  
### DELIVERABLE 4
  
Here, we will create a visualization of the three distinct groups corresponding with the three principal components. We will also create a table with all the currently tradable cryptocurrencies using the *hvplot.table()*.

  * Create a 3D scatter plot using *scatter_3d()* to plot the three clusters from clustered_df. We will also add CoinName to *hover_name* and Algorithm to _hover_data_.
  
  ![3D_plot](https://github.com/SoumyaAbraham/Cryptocurrencies/blob/main/Images/Del4_3Dscatter.png)

  * Use *hvplot.table()* to create a table with the tradable cryptocurrencies
  
  ![hvplot_table](https://github.com/SoumyaAbraham/Cryptocurrencies/blob/main/Images/Del4_hv_table.PNG)
  
  * Print the total number of tradable cryptocurrencies in the clustered_df DataFrame
  * Scale the *TotalCoinSupply* and *TotalCoinsMined* columns between 0 and 1 using the *MinMaxScaler().fit_transform* method. 
  * Add this data along with *CoinName* and *class* columns to a new DataFrame:
  
  ![new_df](https://github.com/SoumyaAbraham/Cryptocurrencies/blob/main/Images/Del4_df.PNG)
  
  * Create a scatter plot using *hvplot* where x='TotalCoinsMined' and y='TotalCoinSupply' by 'Class'
  
  ![scatter_plot](https://github.com/SoumyaAbraham/Cryptocurrencies/blob/main/Images/Del4_scatter.png)
