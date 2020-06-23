# Accelerometer-TAC-Project

## Approach:

This problem is a classification problem. The data itself is clean but because the data is in a time series, some feature engineering will have to be done to map it to a TAC. The time intervals would require investigating, such as the time intervals between accelerometer readings, and the total duration of readings. Some consideration needs to be taken into place for classification, as behavior for each individual may be different for each TAC. Perhaps we can try training and evaluating on individuals first, and then as a whole. After a proper mapping is done for a TAC, a model can be chosen and cross validation can be performed to evaluate the performance of our model We start with a standard logistic regression, and move onto other algorithms such as random forests, SVM, xgboost, and neural networks.


To investigate the dataset, we first match the accelerometer time series values to the TAC intervals. We also split our accelerometer time series values into intervals of 10. We feature engineer values absolute mean and variance, as they may indicate how much “movement” happens. 

After cleaning our data, we do a train test split, scale, and encode. Then we run our models and compute the accuracy and F1 score. In this case, I chose to try a Logistic Regression, Random Forest Classifier, and a single layer Neural Network. 

To further improve our results, it would have been nice to have even more data and even more features. More data, such as more participants or more instances of a night out, would allow our model to generalize better. More features, such as a participants’ weight, gender, and perhaps even baseline movement metrics for a given TAC would likely give our model better predictive power. 

After seeing the original paper, it seems the purpose of the study was to use accelerometer data only. The paper also managed to make 200+ features prior to feature selection. Their accuracy was around 77%, so it is worth investigating whether our results overfit.
 
