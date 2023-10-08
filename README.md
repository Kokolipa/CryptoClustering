# Crypto Clustering
## Project Description:
* Using unsupervised learning to predict if crypto currencies are affected by 24-hour or 7-day price changes. 
* Comparing clustering efficiency between KMean algorithm on a scaled data versus scaled data with PCA. 
* Leveraging the **elbow curve** test to identify the "best fit" for the N number of clusters to be implemented in the KMeans algorithm.
* Answering the following questions: 
    * What is the best value for K as indicated by the elbow curve? 
        * Given the line produced by the Elbow Curve DataFrame, four, the the best value for `k` as the values that follow the nuneric value of four are relatively stabilised.
    * Does it differ from the best k value found using the original data?
        * No it does not differ from the best k value found in the original data.
    * What is the total explained variance for the three principal components? 
        * To find the total explained variance of the three principal components, we simply need to sum the explained_variance_ratio, then multiply it by 100 to showcase the precentage amount. In our case=> 89.5%. Specifically, after implementing PCA the amount of data represented from the source scaled data in precentage is 89.5%.
        ``` python
        print(f"{round(sum(explained_variance_ratio)*100, 2)}%") => 89.5%. 
        ```
    * After visualy analysing the cluster analysis results, what is the impact of using fewer features to cluster data using KMeans?
        *  With PCA, the trade-off is reducing the number of features (data used) at the expense of simplicity. Using PCA, we still managed to explain 89.5% of the data and were able to explain multi-dimensional data in 2Ds. Specifically, we enhanced the clarity of which samples are correlated and which aren't. 
        <br><br>
        As shown above, the PCA plot provides a clearer image of the clusters that correlate so we can differentiate between them. However, when PCA is not implemented, it is much more difficult to distinguish between the clusters that correlate. Specifically, cluster 2 appears to correlate with cluster 1 when it doesn't. 


### Description of the data: 
The data includes columns that describe price changes at 24 hours, 7-days, fourtnightly change, 30-days change, 60 days change, 200-days change, and 1-year change.
<br><br>
When describing the data, the variety of the data was expected. The more days go by the more significnt the price changes are. 

``` python
list(df_market_data.columns)
# Output => 
#   ['price_change_percentage_24h',
#  'price_change_percentage_7d',
#  'price_change_percentage_14d',
#  'price_change_percentage_30d',
#  'price_change_percentage_60d',
#  'price_change_percentage_200d',
#  'price_change_percentage_1y']

```
### ETL
#### Extract: 
* Extracting the CSV crypto data from the folder and rendering it into Jupyter notebook.
#### Transform: 
* Standardising and normalising the data using the StandardScaler from Sklearn. 
* Reducing the amount of features using decomposition - PCA from Sklean.
#### Load: 
* Load the data (CSV) into Jupyter for analysis.


#### Python Libraries Used:
1. Pandas.
2. Sklearn - cluster (KMeans), decomposition (PCA), preprocessing (StandardScaler).
3. Hvplot.
4. Matplotlib.


#### Folder structure
``` yml
.
│   ├── Starter_Code 
│   |   ├── Resources   
│   |   |   ├── crypto_market_data.csv    
│   |   ├── Crypto_Clustering.ipynb              
|___README.md    
|.gitignore          
``` 