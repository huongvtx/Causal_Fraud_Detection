# Causal_Fraud_Detection

This project seeks to implement a Bayesian network based approach to fraud detection in banking. This is done by learning causal relationships across variables via estimation of their conditional independence. This network contains one or multiple Directed Acyclic Graphs (DAGs), each representing immediate and non-immediate relationships around single variables. One can refer the network to a personal family tree in which various persons are connected by arrows to showcase parents, children, siblings, and so on.

Since the number of possible causal structures increases exponentially upon larger sets of features, there have been numerous algorithms introduced to find an optimal structure from input datasets. In this experiment, I demonstrate the use of PC algorithm to learn a global structure of all variables (excluding target variable) and PC-simple algorithm to extract immediate features (nodes) surrounding the labelled class.

The dataset in use contains 1 million observations and 32 variables, both numeric and categorical. The dataset can be found at https://www.kaggle.com/datasets/sgpjesus/bank-account-fraud-dataset-neurips-2022/data?select=Base.csv

In overall, the experiment includes:
- Preprocessing: One hot coding of categorical variables and Min-Max standardisation of numeric features, resulting in a whole numeric dataset.
- Constructing a global BN: A complete partially DAG is learned with all predictors, yielding a structure of 257 directed and 15 undirected edges.
- Predicting fraud: A set of 17 variables is selected to input into a Naive Bayes classifier, tuned with 10-fold cross validation, SMOTE resampling, and kernel density estimation, finally obtaining the accuracy of 0.95.

Below is an excerpt of the global BN structure, showing complex associations among fraud-related factors. A full view can be obtained from the attached file.

![image](https://github.com/user-attachments/assets/e8e02893-650c-4824-a3e6-c09af6ad51bd)
