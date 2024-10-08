# Problem Statement
The business objective is to identify whether or not customers will subscribe a term deposit with the bank. In order to identify this, we will train several different types of classifiers on the dataset, and evaluate which one performs best at classifying whether a customer will subscribe or not.

# Findings
The table below contains the results from the 4 different model types I evaluated, including their performance and the best hyperparameters I found for each model type.

|   | Train Score  | Test Score  | Best Parameters  |
|---|---|---|---|
| Logistic Regression  | 0.90042  | 0.90078  | C=5.0  |
| KNN  | 0.90236  | 0.89747  | leaf_size=10, n_neighbors=20  |
| Decision Tree  | 0.90919  | 0.89860  | max_depth=10, min_samples_leaf=15, min_samples_split=15  |
| SVM  | 0.89782  | 0.89682  |  C=1.0, degree=2 |

Based on this, I believe that on the margin, logistic regression is the best choice for classifying the data. It's able to classify customers with 90% accuracy, which is an improvement over the baseline of 88% (which was established by predicting on call duration--a highly predictive feature that would not be practically usable in our business case).

# Next Steps and Recommendations
In order to boost efficiency of sales calls (and avoid wasting time on customers who aren't likely to buy), I would recommend using a logistic regression classification model to predict whether all customers on the client list are likely or not to subscribe. Sales reps can then focus on starting with the likely-to-deposit customers, and dedicate more time and energy to answering their questions and providing whatever additional services are required to close the deal. Customers who are classified as unlikely to deposit should not be completely ignored of course--but if a sales rep knows going into the call that the customer isn't currently likely to sign up, they can be prepared to put in additional effort in persuading and addressing the core issues that prevent the customer from depositing. 
