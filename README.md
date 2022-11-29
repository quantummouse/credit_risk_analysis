# Credit Risk Analysis
In this excercise, I am using machine learning to determine credit card risk by using different algorithms and comparing their performance. 
The credit card data is from LendingClub, a lending services company. Two of the oversampling algorithms were RandomOverSampler and SMOTE. SMOTEEN is combination of over and under sampled algorithms. The two ensamble classifiers BalancedRandomForestClassifier and EasyEnsembleClassifier were used as well to compare how they identify high risk creditors. 

The process for each one was similar - Resampled data was split into train and test data sets, used to train a regression model, balanced accuracey score was calcluated, as well as confusion matrix was generated. Classification report was then generated as well. Random state of 1 was used to generate the same values between tests.
- Accuracy - base metric usually used for machine learning and it measures the number of of correct predictions over all predictions.
- Precision - measures how many of the POSITIVE predictions are actually Correct /true possitive. 
- Recall - measure of how many positive cases the classifier correctly identified over ALL the positive cases in the data set. 
- Specificity - measure of how many negative predictions were made correctly (true negatives)
- F1 score measures combined precision and recall as an average of the two measures. 

# Overview and purpose

## Results - balanced accuracy score, precision and recall scores
### Oversampled
1. RandomOverSampler
Accuracy = 0.6351
                  pre       rec       spe        f1       geo       iba       sup
  high_risk       0.01      0.74      0.63      0.02      0.69      0.48       101
   low_risk       1.00      0.63      0.74      0.78      0.69      0.47     17104
avg / total       0.99      0.64      0.74      0.77      0.69      0.47     17205

2. SMOTE
Accuracy = 0.6689
                  pre       rec       spe        f1       geo       iba       sup
  high_risk       0.01      0.63      0.67      0.02      0.65      0.42       101
   low_risk       1.00      0.67      0.63      0.80      0.65      0.43     17104
avg / total       0.99      0.67      0.63      0.80      0.65      0.43     17205

### Undersampled
3. ClusterCentroid
Accuracy = 0.6514
                  pre       rec       spe        f1       geo       iba       sup
  high_risk       0.01      0.69      0.39      0.01      0.52      0.28       101
   low_risk       1.00      0.39      0.69      0.57      0.52      0.27     17104
avg / total       0.99      0.40      0.69      0.56      0.52      0.27     17205

4. SMOTEEN - Combination over and under sampled
 Accuracy = 0.5439
                  pre       rec       spe        f1       geo       iba       sup
  high_risk       0.01      0.65      0.59      0.02      0.62      0.39       101
   low_risk       1.00      0.59      0.65      0.74      0.62      0.39     17104
avg / total       0.99      0.59      0.65      0.74      0.62      0.39     17205

### Ensamble Learners
5. BalancedRandomForestClassifier
Accuracy =0.7878
                  pre       rec       spe        f1       geo       iba       sup
  high_risk       0.04      0.67      0.91      0.07      0.78      0.59        87
   low_risk       1.00      0.91      0.67      0.95      0.78      0.62     17118
avg / total       0.99      0.91      0.67      0.95      0.78      0.62     17205

6. EasyEnsembleClassifier
 Accuracy =0.9254
                  pre       rec       spe        f1       geo       iba       sup
  high_risk       0.07      0.91      0.94      0.14      0.93      0.85        87
   low_risk       1.00      0.94      0.91      0.97      0.93      0.86     17118
avg / total       0.99      0.94      0.91      0.97      0.93      0.86     17205

## Summary of the results 
EasyEnsembleClassifier seemed to have performed the best when compared to others, based on scores in Accuracy, Recall, Specificity and F1 metrics. In the credit risk scenario it is important to properly identify high risk accounts so having recall at .91 is a good sign. Specificity would also be helpful, as identifying low risk accounts propertly means that the credit company isn't classifying someone as high risk who could actually be helpful to do business in the future and lend them money. 
High accuracy of 92% of Easy Ensamble Classifier is a good indicator for the overall algorithm. F1 score was higher for high risk borrowers than other algorithms. Precision of identifying high risk credit risk was higher with this classifier as well. 

