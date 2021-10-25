## Banking Churn Classification Analysis

The purpose of this project is to create a classification model that will predict whether a bank customer will churn. The aim of this project is to increase precision as much as possible through the trial of many different classification models. With high precision we will be minimizing false positives and be increasing the certainty that our positives are actually people that will churn. This will allow for better utilization of limited customer service resources to directly reach out to potential churning customers. 

Currently, three models have been fit to the training data. Below is the confusion matrix for the K Nearest Neighbors model. After 10 neighbors were found to be the optimal number, a precision score of 66.3% was achieved. 

![](Images/KNN_Confusion.png)

Below is the confusion matrix for the Logistic Regression classification model. With little regard for recall the precision score was found to be 57.8%.

![](Images/LR_Confusion.png)

The last model that has been run is the Decision Tree Classifier. With holding the maximum depth at 7 the model does not overfit and a precision score was 73.9%. Currently, the best model is the Decision Tree Classifier and more models will be tested in future analysis.

![](Images/DC_Confusion.png)

