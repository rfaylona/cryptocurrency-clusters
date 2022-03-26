# Cryptocurrency Clusters
![eamesBot/Shutterstock.com](Resources/Images/crypto.jpeg)
## Scenario

* I are on the Advisory Services Team of a financial consultancy. One of my clients, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. They’ve asked me to create a report that includes what cryptocurrencies are on the trading market and determine whether they can be grouped to create a classification system for this new investment.

* I have been handed raw data, so you will first need to process it to fit the machine learning models. Since there is no known classification system, I will need to use unsupervised learning. I will use several clustering algorithms to explore whether the cryptocurrencies can be grouped together with other similar cryptocurrencies. I will use data visualization to share my findings with the investment bank.

### Data Preparation

* Read `crypto_data.csv` into Pandas. The dataset was obtained from [CryptoCompare](https://min-api.cryptocompare.com/data/all/coinlist).

* Discarded all cryptocurrencies that are not being traded. 

* Removed all rows that have at least one null value.

* Filtered for cryptocurrencies that have been mined. That is, the total coins mined should be greater than zero.

* In order for the dataset to be comprehensible to a machine learning algorithm, its data should be numeric. Since the coin names do not contribute to the analysis of the data, deleted the `CoinName` from the original dataframe.

* Converted the remaining features with text values, `Algorithm` and `ProofType`, into numerical data. To accomplish this task, used Pandas to create dummy variables.

* Standardized the dataset so that columns that contain larger values do not unduly influence the outcome.

### Dimensionality Reduction

* Creating dummy variables above dramatically increased the number of features in your dataset. Performed dimensionality reduction with PCA. For this project, preserved 90% of the explained variance in dimensionality reduction. 

* Next, further reduce the dataset dimensions with t-SNE and visually inspected the results. In order to accomplish this task, ran t-SNE on the principal components: the output of the PCA transformation. Then created a scatter plot of the t-SNE output. Observed whether there are distinct clusters or not.

### Cluster Analysis with k-Means

* Created an elbow plot to identify the best number of clusters. Used a for-loop to determine the inertia for each `k` between 1 through 10. Determine, if possible, where the elbow of the plot is, and at which value of `k` it appears.

### Recommendation

* Based on my findings, cryptocurrencies can be cluster into 4 distinct groups as proven with the dataset provided.