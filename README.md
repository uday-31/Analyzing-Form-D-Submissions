# Analyzing Form D Submissions

Used nonlinear dimension reduction, clustering, nonparametric smoothing, and natural language processing to analyze Form D submissions from SEC's website.

This project was done for the requirements of the class 46-923 Financial Data Science II, along with my group members Dhruv Baid, Guolun Li, Shangyu Li, and Yi Xin Xiang.

# Introduction

We obtained the data from the SEC website, as a part of their Form D datasets. It contains information on the Form D submissions filed by companies in their EDGAR document submissions.

The data required extensive cleaning. Out of the 41 columns, 26 had one or more missing values. In tackling these missing values, we used the following philosophy: we made a distinction between not knowing something versus knowing that something is not applicable. NaNs represented “lack of data”, or cases where the actual value was unknown. If something was not applicable, we filled it in with “Not Applicable” instead, since the fact that something was not applicable was additional information in itself, and was included in the analysis. We also looked at the actual Form D to impute some of the missing boolean values.

Then, we answered the following questions:
1. Are there variables in the data set that could help predict the percentage of offering sold?
2. To what extent does Investment Fund Type influence the properties of the offering such as Revenue Range, Total Offering Amount?
3. How does the relationship between the total amount sold and the total number of people who have already invested vary with the sale date?
4. Is there a change in the minimum investment accepted over time, and does this vary with industry?

# Question 1
To answer this question, we used Natural Language Processing and K-Means Clustering. After finding clusters with firms that had similar offerings sold, we analyzed the textual fields using NLP to identify common characteristics that had some predictive power.

# Question 2
We answered this question using clustering (Agglomerative, K-Means, and Hierarchical). This allowed us to quickly, and visually, identify patterns in the data.

# Question 3
To answer this question, we used nonparametric regression. To do so, we divided the entire dataset into different bins of time, and fit a nonparametric curve to each time period. This allowed us to identify the change across time.

# Question 4
We answered this question using hypothesis testing. After deriving the expression mathematically, we conducted the Likelihood Ratio (LLR) and Mann-Kendall (MK) tests to determine if there was any trend in the time series.
