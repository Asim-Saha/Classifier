This module compares 4 common classifiers for binary classification
* KNN
* Decision Trees
* Logistic Regression
* Support Vector Machines
on a sample data set provided. The data set is from a direct-marketing campaign carried out on behalf of a bank, with the objective to get customers to sign up for a long-term bank deposit. The target feature - yes or no - indicated whether or not a customer that received one or more phone calls from a bank representative signed up for the deposit. The stated purpose of the study that led to the data collection was to be able to continue to carry out direct marking campaigns but require fewer contacts per customer, while maintaining the same rate of subscription (saying yes) to the offered product.

Overview

The analysis begins by establishing a baseline model, which is given by the majority class ,  classifiers is developed, then optimized, at each point comparing the performance against the baseline.

Modeling Approach

Next, a logistic regression is performed, using all default parameters. The logistic regression achieves just slightly higher performance than the trivial (baseline) model.

Comparing Non-Optimized Classifiers

The performance from the logistic regression is then compared to the same obtained by 3 additional classifiers - KNN, Decision Trees, and Support Vector Machines. The results from these classifiers, as well as the time to fit and score the models, is collected in a dataframe for ease of comparison.

Optiziming the Classifiers

Lastly, these same 4 classifiers are subject to a hyperparameter search using grid search, over a range of specified hyper-parameter values. 

Findings

The KNN classifier was computationally prohibitive on the full data set. Although it was fast to fit, its prediction stage took so long that it needed to be interrupted (stopped). On smaller subsets of the data, I found it was on par performance wise with other classifiers, not notably better or worse.
The logistic and SVC classifiers got about the same performance, but the SVC was dramatically slower to fit than the logistic regression. On this data set, if these were the only 2 classifiers available, the logistic regression would be the better choice, because it was much faster to operate.
The decision tree got the best overall performance and was also the fastest to fit and score, achieving a balanced accuracy of 74% over the test set. I used balanced accuracy, not accuracy, as the target scoring function to optimize over because the data set was highly imbalanced.
# Classifier