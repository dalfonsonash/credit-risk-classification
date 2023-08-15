# Module 20 Analysis

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* The purpose of this analysis was to build a model to determine the creditworthiness of borrowers using data comprised of historical lending activity.
* The provided data contained variables including loan amount, interest rate,	borrower's income,	debt to income ration, number of open accounts,
  derogatory marks, and	total debt.  The goal of the models was to predict the borrower's risk profile.
* The variables I was trying to predict, e.g., 'value counts', is as follows: Class "0" (healthy loans)= 75036 instances, and Class "1"(high-risk loans)= 2500 instances.
  This demonstrates a class imbalance with healthy loans significantly outweighing high-risk loans.  The imbalance could lead to a biased model performance, as the model
  may become more biased toward predicting the majority class.  The class imbalance was addressed by using oversampling, which helps the model learn better from the minority
  class and potentially improve its performance in identifying truly high-risk loans.
* The stages of the machine learning process of this analysis include the following:
  * Data Loading: loading the lending data CSV file into a pandas dataframe.
    Data Preprocessing: Separating the labels (target variable) and features (input variables) and splitting the data into training and testing sets. RandomOverSampler was used to address
    class imbalance.
  * Model Initialization: Logistic Regression model using the LogisticRegression class from the sklearn.linear_model module. A random state was assigned to ensure reproducibility in the model's behavior.
  * Model Training: Trained the Logistic Regression model using the training data. This involved using the .fit() method to allow the model to learn patterns from the data and adjust its parameters accordingly.
  * Model Evaluation: Evaluated the model's performance using various metrics. The accuracy score was calculated, generated a confusion matrix, and printed the classification report to get insights
    into the model's precision, recall, and F1-score for each class.
  * Oversampling: Addressed the class imbalance by oversampling the training data using the RandomOverSampler from the imbalanced-learn library. This helps to improve the model's ability
    to learn from the minority class.
  * Model Evaluation with Oversampled Data: After oversampling, I evaluated the model again using the same metrics as before. This allowed for a comparison between the model's performance
    with and without addressing the class imbalance.
* LogisticRegression: This method helped in determining if the loan was classified as healthy or high-risk.
  
## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1 (class_report):
  * Description of Model 1 Accuracy, Precision, and Recall scores:
    Accuracy: 0.99
    Precision for Class "0" (healthy loans): 1.00
    Recall for Class "0": 0.99
    Precision for Class "1" (high-risk loans): 0.85
    Recall for Class "1": 0.91



* Machine Learning Model 2 (resampled_report):
  * Description of Model 2 Accuracy, Precision, and Recall scores:
    Accuracy: 0.99
    Precision for Class "0" (healthy loans): 1.00
    Recall for Class "0": 0.99
    Precision for Class "1" (high-risk loans): 0.84
    Recall for Class "1": 0.99

## Summary

Both models achieve a high level of accuracy, which indicates their overall effectiveness in classifying loans. The precision and recall scores for both classes are also impressive, with only slight variations between the models. The resampled model exhibits a small drop in precision for high-risk loans (class "1"), but it maintains high recall for the same class.

Choosing the best model depends on the specific goals and priorities of the problem at hand:

Balanced Performance: If you aim for a balanced performance in identifying both healthy and high-risk loans, both models are strong contenders. The original model maintains a slightly higher precision for high-risk loans, while the resampled model achieves slightly better recall for the same class.

Consideration for High-Risk Loans: If correctly identifying high-risk loans (class "1") is of paramount importance, the resampled model might be more suitable due to its higher recall for that class. A higher recall in this context means that the model captures a larger proportion of actual high-risk loans.

Consideration for Overall Accuracy: If achieving the highest overall accuracy is crucial without leaning too heavily towards any specific class, both models offer equally strong accuracy.

Given the similarity in performance, you might consider using the resampled model due to its slightly better recall for high-risk loans. However, the choice between the two models ultimately depends on the specific goals of your analysis and the problem you're trying to solve.
