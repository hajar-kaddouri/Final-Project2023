# Final-Project2023
![image](https://github.com/hajar-kaddouri/Final-Project2023/assets/125761572/6931c387-4b06-423c-befd-674e65cece36)
                            A Deep Dive into Advanced Anomaly Detection Techniques


### Comprehensive Anomaly Detection Framework (CADF-2)
# Overview
The Comprehensive Anomaly Detection Framework 2 (ComprehensiveAnomalyDetection2) is designed with OOP to identify anomalies in transactional data. It leverages various statistical and machine learning techniques, including rolling statistics, KMeans clustering, and ensemble models, to efficiently detect unusual patterns.

Anomaly detection is a technique used to identify unusual patterns that do not conform to expected behavior, called outliers. It has many applications in business, from intrusion detection (identifying strange patterns in network traffic that could signal a hack) to system health monitoring (spotting a malignant tumor in an MRI scan), and from fraud detection in credit card transactions to fault detection in operating environments.

Anomaly detection is similar to — but not entirely the same as — noise removal and novelty detection.

In this jupyter notebook, we are going to take the credit card fraud detection as the case study for understanding the Advanced Anomaly Detection Techniques used.

# Exploratory Data Analysis (EDA):

An EDA has been previously conducted on the dataset which provided us with insights into the data distributions, relationships, and preliminary patterns that guide the subsequent feature engineering and modeling steps.

# Features
The primary feature columns being considered by the framework are:

transaction_dollar_amount: The amount in dollars for a particular transaction.
Long: Longitude where the transaction occurred.
Lat: Latitude where the transaction occurred.
credit_card_limit: Limit on the credit card being used.

# Methods Description

1- Anomaly Detection Techniques:

The approach used in this notebook is identifying irregularities in data to flag the data points that deviate from common statistical properties of distribution, including mean. the definition of an anomalous in this case is a data point that deviates by a 3 standard deviation from the mean.

I was in need of a rolling window to compute the average across the data points. Technically, this is called a rolling average or a moving average, and it's intended to smooth short-term fluctuations and highlight long-term ones, so I used 7 days as short -term period and I did also 30 days to see the difference but 7 days gives a better result.

2- Machine Learning-Based Approaches:

Below is the machine learning-based techniques used for anomaly detection.

a. Density-Based Anomaly Detection Density-based anomaly detection is based on the k-nearest neighbors algorithm.

Assumption: Normal data points occur around a dense neighborhood and abnormalities are far away, the model detecte around 2000 cases of the anomaly but due to the limited capacity of my computer I replace it with the k-mean model.

b. Clustering-Based Anomaly Detection Clustering is one of the most popular concepts in the domain of unsupervised learning.

I use it to identify the data points that are similar and tend to belong to similar  clusters, as determined by their distance from local centroids, and then create labels based on the clusters found (0-1)

2-means similar clusters of data points. Data instances that fall outside of these groups could potentially be marked as anomalies (=1).

3-combine anomalies:

from the previous 2 approaches I create a new column that included the label that is 1 in both techniques and mark other as 0, and with combination i was able to switch my data frame to label data frame that can indicate (fraud, non-fraud).


4- ensemble_models:

Uses ensemble models like Random Forest and Gradient Boosting Trees to identify anomalies. SMOTE oversampling is applied to the training data to address class imbalance.

# Conclusion :


![image](https://github.com/hajar-kaddouri/Final-Project2023/assets/125761572/7ef91d5e-ca05-4756-9611-fe4d438cda86)

# Future Work

- Applying advanced neural networks.
- Integration with real-time data streams.
- Further fine-tuning of hyperparameters.

  ***Open for any queries, discussions, or collaborations ** 
