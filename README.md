# Machine_Learning_ADominguez

## Summary of Project:

Building and evaluating several machine learning models to assess credit risk, includes: Training a logistic regression classifier, calculating the balanced accuracy score, generating a confusion matrix and printing the classification report.


## Summary and analysis of the models’ performance:

#### Random OverSampling
                  pre       rec       spe        f1       geo       iba       sup

  high_risk       0.01      0.64      0.63      0.02      0.64      0.41        87
   low_risk       1.00      0.63      0.64      0.77      0.64      0.40     17118

avg / total       0.99      0.63      0.64      0.77      0.64      0.40     17205

In random oversampling, instances of the minority class are randomly selected and added to the training set until the majority and minority classes are balanced. The accuracy score measures the performance of a aclassifier, so for a score of 64% in this model the performance of the classifier isn't that impressive. Though accuracy is not a good metric when the data is imbalanced. Precision and recall shows low values as well, and a low precision means there are a lot more false positives in the data. For the True Positive Rate(recall) it measures the classifier's completeness, and therefore a low value recall such as above, indicates a high number of false negatives 


#### SMOTE 
                  pre       rec       spe        f1       geo       iba       sup

  high_risk       0.01      0.61      0.68      0.02      0.64      0.41        87
   low_risk       1.00      0.68      0.61      0.81      0.64      0.41     17118

avg / total       0.99      0.68      0.61      0.80      0.64      0.41     17205

While recall values in the SMOTE model, is a little better in the low-risk pool than in the random-oversampling, it is not by much. Like the Random Oversampling, precision is dismal, meaning in both risk pools meaning there are a lot of false positives (precision) amd false negatives(recall) in this data as well. The balanced accuracy score is about 66%, not much greater than that in the previous model.

In both Oversampling examples above (SMOTE & Random Over Sampling) it is important to note that one model does not outperform the other. In fact their metrics and performance are about the same. Plus SMOTE is vulnerable to outliers.



#### Cluster Centroids Algorithm
                   pre       rec       spe        f1       geo       iba       sup

  high_risk       0.01      0.63      0.39      0.01      0.50      0.25        87
   low_risk       1.00      0.39      0.63      0.56      0.50      0.24     17118

avg / total       0.99      0.39      0.63      0.56      0.50      0.24     17205

Similar to SMOTE is the Cluster Centroids Algorithm/Model. Centroids represents the clusters of generated data points of a majority class. With balanced accuracy metric approximating 66% the performance of the classifier is very similar to that of the SMOTE model. 
The one conclusiojn is that resampling does not gurantee better results.


#### SMOTEENN Algorithm
                   pre       rec       spe        f1       geo       iba       sup

  high_risk       0.01      0.72      0.59      0.02      0.65      0.43       101
   low_risk       1.00      0.59      0.72      0.74      0.65      0.42     17104

avg / total       0.99      0.59      0.72      0.74      0.65      0.42     17205

In SMOTEENN we see that some of the metrics show an improvement. The recall for the high-risk pool example, is 72% that is the highest we have seen in all 4 sample models. The precision metrics is same as indicated in all 3 other models. The accuracy score is also approximately 66%.


####  Final recommendation

The above metrics are so very similar throughout the different models, it is almost impossible to recommend one over the other.
That said, I would recommend the SMOTEENN algorithm since that combines aspects of both the oversampling and undersampling, which eliminates some of the challenges found in solely oversampling or undersampling alone. 

