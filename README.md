# Project Motivation and Scope
Startups are becoming more prevalent in the digital age. The Internet provides many opportunities for people to start businesses in the software and services space, for instance. However, for investors, it is challenging to determine the prospects of a given startup.

To address this, we aim to produce a machine learning model that can predict startup success based on metrics like number of funding rounds, funding total, and the year the startup was founded. We define success as a startup that has acquired, ipo, or operating (conditional) as its status. To be considered a success, operating status has to be accompanied with a funding total above the median of all operating startups. This leaves us with a binary classification problem.

We take a data set from https://www.kaggle.com/datasets/manishkc06/startup-success-prediction with 923 startups. However, due to the limitations in observations, we merged it with a larger data set by looking at common columns and removing duplicates. https://github.com/datahoarder/crunchbase-october-2013. We end up with a total of 8000+ entries.

# Exploratory Data Analysis

Exploratory Data Analysis demonstrated problems with skewness and outliers, which we removed using Box Cox transformation and 1.5*IQR respectively. Based on the graphs, we also identified features to remove from the data set. From there, we tested multiple classifiers with their default parameters using Stratified K Folds cross validation. The top three performing models (based on accuracy and roc_auc) are chosen for use in ensembling.

# Modelling Techniques 

We identified Gradient Boosting, AdaBoost, and Random Forest as the top performing classifiers. We then ran Randomized Search to determine the best hyperparameters for each model. We visualized Feature Importance to investigate the significance each variable has in a given model. Each model is scored by accuracy to determine if any individual model can beat the ensemble.


# Model Improvements
We create two ensembles: VotingClassifier and StackingClassifier. The ensembles are scored by accuracy as well. We conclude that the StackingClassifier outperforms all other competing models.

To complement our initial project motivation, we evaluate the potential earnings (True Positives and Negatives) and costs (False Positives and Negatives) from relying on our model.

# Individual Contributions
EDA, interpretation, feature selection - Kanupriya and Mihika

Feature engineering, cross val, and modelling - Caleb

Presentation - Kanupriya and Mihika


