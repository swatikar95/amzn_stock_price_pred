### Project Overview
This script contains a real-world stock price dataset (Amazon) collected from Yahoo Finance. I have applied three machine learning algorithms on this dataset: Logistic Regression, Decision Tree, and Random Forest.

### Results
#### Logistic Regression

![Logistic Regression Results](/images/output1.png)

The image shows an ROC curve for a logistic regression model with an AUC of 0.54. This AUC value is close to 0.5, indicating that the model does not perform much better than random guessing on the test dataset. The curve is slightly above the diagonal line (which would represent a completely random classifier), suggesting a minimal ability to distinguish between the two classes.

#### Decision Tree Classifier

![Decision Tree Results](/images/output2.png)

The image depicts an ROC curve for a decision tree classifier with an AUC of 0.59. This is a slight improvement over logistic regression in terms of model discrimination ability. The curve steadily increases and is consistently above the diagonal line, indicating better performance than random guessing but still limited effectiveness.
#### Random Forest Classifier

![Random Forest Results](/images/output3.png)

This image shows the ROC curve for a random forest classifier, which achieves an AUC of 0.69. This indicates a moderate predictive power and a better performance compared to the other two models. The curve is steeper in the beginning and levels off as it approaches the top-right corner, suggesting that the random forest model is more effective at distinguishing between the positive and negative classes.

