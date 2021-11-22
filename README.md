# CMPE 255 - Term Project 
## Title: Exploratory Data Analysis on Behavioral Risk Factor Surveillance System 

### Introduction:
- This project identifies how an individual’s features, daily activities, and existing health conditions can impact their probability of contracting different diseases. 
- The activities that we do in our everyday life, economic standing, gender, and age impact our health and personality. 
- With the help of the BRFSS dataset provided by the Centers for Disease Control and Prevention (CDC), this project explores the correlation between an individual’s attributes and their diseases. 
- The project aims to develop data-driven insights to assist individuals in devising effective and accurate long-term strategies to mitigate the probability of them contracting a particular disease. 
- On a large scale, these insights can help policymakers and communities develop effective policies for all individuals. 

---------------------------------

### Disease of interest:
(1) Lung issues

(2) Heart issues

---------------------------------

### Approach:

Step-1) We apply different statistical and data-dependent dimensionality reduction techniques for preprocessing and faster model generation over basic manual selection.
  - We drop derived columns (names start with underscore).
  - We drop columns with little information, ie. the columns with low standard deviation.
  - We drop all columns with mostly null values.
  - We drop all the columns with datatype as object (since all other columns are float64)
  - We find all missing values in the matrix. Think of what to replace them with (-1 ?). Need to replace them before dimensionality reduction.
  - We perform Correlation-based Dimensionality Reduction.
  - Based on correlation between columns, we if two columns have a correlation > 90%, we consider the first column and drop the second one.
  - Finally, go through leftover columns and remove columns which do not belong to target disease by manually selection.
  
Step-2) We split data into train & test set.

Step-3) We compare multiple classification algorithms best suited for the problem. 
  - Logistic Regression algorithm
  - Decision Tree algorithm
  - Random Forest algorithm
  - Gaussian Naive Bayes algorithm
  - XGBoost algorithm

Step-4) We compute the accuracy, recall & F-1 score for each algorithm's prediction. Ideally, we want the algorithm with highest accuracy and recall = 1.

Step-5) We finally try to generate interesting insights about how various health issues are correlated to various types of categories of people in the dataset. Achieve this by analyzing the relationship between various features for a particular health issue.

---------------------------------

### Data:

[Kaggle dataset from 2015](https://www.kaggle.com/cdc/behavioral-risk-factor-surveillance-system)
