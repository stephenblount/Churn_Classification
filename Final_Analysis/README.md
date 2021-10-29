## Abstract:

There is a notion that it costs five times more to acquire a new customer than to retain one. Due to this fact, modeling churn is an important task for businesses to undertake. The objective of this analysis is to model customer churn for a banking establishment. The goal is to create a classification model that will classify customers as exited or retained. With the ability to predict if a customer is likely to exit before actually exiting, preventative measures can be taken. Many classification models were fit to the data and the extreme gradient boost classification model was found to have the highest ROC AUC score. Two approaches were found for this classification analysis. The first was to maximize recall to capture as many true positives (people predicted to exit that exited) as possible and minimize false negatives (people predicted to stay that exited). The second was to maximize precision and minimize false positives (people predicted to exit that stayed). The former approach is more easily implemented and a blanket retention fee can be associated with all true positives and false positives. The approach saved the bank $86,850. The latter looks at a customer's lifetime value and targets customers with a high account balance to be retained. 

## Churn Modeling

The churn banking data was collected from Kaggle and contained 14 features and 10,000 rows. The features included age, geography, balance, salary, tenure, is active, number of products, sir name, gender, credit score, and has credit card. The data was explored using different diagnostic plots. From these plots it was found that age had the highest separation of groups for the target variable. Additionally, balance was right skewed, with many account balances having a zero dollar value. To account for this, balance was binned into three categories, high, mid, and zero. All categorical features were then encoded and all data was normalized prior to analysis. 

The first approach for this analysis was to try to maximize recall.  Maximizing recall captures as many true positives (people predicted to exit that exited) as possible and minimizes false negatives (people predicted to stay that exited). This will allow for the largest number of people predicted to churn to be targeted for a promotion campaign to prevent customer departure. A 5:1 ratio was used for the cost to acquire a new customer versus retain an existing customer. The values used were $750 for acquisition and $150 for retention. The philosophy was if a customer churned (false negative) the bank would incur a cost of $750. If a customer that was exiting and then was retained (true positive), the bank would incur a cost of $150 for a retention fee and save $750 for not having to acquire another customer, for a net gain of $500. If a customer was retained and predicted to be exiting (false positive), the bank would incur a cost of $150 dollars for a retention fee. Two baseline models were created, one captured the effects of doing nothing and one captured the effect of retaining everyone. These metrics were used as a bounding box to determine the performance increase of a predictive model. The extreme gradient boosted model was found to have the best recall versus precision balance that netted the highest profit. With the XG boost model at a threshold of 0.07, $86,850 was saved for the bank. The downfall to this approach is that there are many false positives; money is being spent on retention promotions that does not need to be. Additionally, there is such a thing as an unprofitable customer and a bank might want to let unprofitable customers churn. 

The second approach of this analysis was to try to maximize precision. Maximizing precision minimizes false positives (people predicted to exit that stayed) and increases the confidence that a positive is a true positive. Using the XG boost model with a threshold of 0.9, the event rate (% of positive class located within the threshold range) was 97.7%. These customers could be sorted by account balance. A team of customer service representatives could work to retain the customers with high account balances with little fear that these customers were false positives and let unprofitable customers with low balances churn. Additional analysis would need to be undertaken to put a dollar amount on the customer’s lifetime value. 