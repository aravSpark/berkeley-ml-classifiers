Berkeley AI/ML course assignment, comparing classifiers

### Problem statement

The objective of this task is to compare and identify a model that explains which prospective clients are likely to respond positively to a direct marketing campaign and subscribe to a term deposit. Using historical client, contact, and economic data, the goal is to predict which customers are more likely to subsribe. This helps the bank focus on high-potential clients, lower campaign costs, and make future marketing campaigns more targeted and data-driven.

In real-world settings, such models allow organisations to target the right prospects at the right time, allocate staff and budget more efficiently, and understand the key drivers of customer behaviour. This supports more personalised communication and improve conversion rates while reducing overall campaign effort.

### Dataset
Our dataset comes from the UCI Machine Learning repository [link](https://archive.ics.uci.edu/ml/datasets/bank+marketing). The data is from a Portugese banking institution and is a collection of the results of multiple marketing campaigns.

### Link to notebook

[Notebook](https://github.com/aravSpark/berkeley-ml-classifiers/blob/main/prompt_III.ipynb)  

### Methodology

The CRISP DM framework guided the analysis to understand which factors influence subscription and to compare different classification methods.

Activities included:

- Data exploration to understand distributions, imbalance, and feature quality
- Visualisation of numeric and categorical features
- Preprocessing and encoding with a ColumnTransformer
- Building and comparing several classification models
- Evaluation using accuracy, precision, recall, F1 score, and AUC
- Hyperparameter tuning for selected models with GridSearchCV
- Conclusion based on model performance and EDA

### Modelling

Baseline

Majority class classifier (predict all "no"). Baseline accuracy is about 88 percent due to heavy class imbalance.

**Models tested**
- Logistic Regression
- K Nearest Neighbors
- Decision Tree
- Support Vector Machine

**Tuning**
- KNN tuning of number of neighbors and weighting
- Decision Tree tuning of depth and minimum samples per leaf

Scoring based on AUC to address class imbalance

### Model Evaluation
Best performing tuned models
- Tuned Decision Tree achieved the highest AUC (~0.66)
- Tuned KNN achieved moderate AUC (~0.60)

Accuracy remained near the baseline for all models because the dataset is dominated by negative outcomes.
AUC and precision improved slightly after tuning, but recall remained low for all models.

### Findings

- Client attributes alone provide limited predictive value.Most models perform only slightly above the majority baseline.
- AUC is more informative than accuracy. Tuned Decision Trees provided the best ranking performance.
- Low recall indicates difficulty identifying clients who will subscribe.

### Recommendations

- Campaign interaction features, such as call duration, previous contact outcomesand time since last contact klikey have stronger predictive power but were excluded in this iteration. 
- Economic context and timing should be considered when planning campaigns.
- Target high potential prospects early on rather than repeated follow ups.

