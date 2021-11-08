# Credit_Risk_Resampling
In this Challenge, I’ll use various techniques to train and evaluate models with imbalanced classes. I’ll use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.


## Overview of the Analysis

* The purpose of the analysis is to use historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers; accurately perdict risky loans . This is an inhernitly imbalanced problem because there are more 'healthy'loans (status 0) than there are 'risky' loans in the origianl data set. 

* The origial data set contained 75036 healthy loans and 2500 risky loans.

* The Original Data is an imbalancesd data that is composed of:
    * 75036 loans with  a "healthy" loan status of '0'
    * 2500 loans with a "risky" loan status of '1' 

* The stages of the machine learning process undertaken consisted of: 

  * Spliting the Data into Training and Testing Sets

  * Creating  a Logistic Regression Model with the Original Data

  * Predict a Logistic Regression Model with Resampled Training Data 

## Results

* Machine Learning Model 1: Logistic Regression Model with Original Imbalanced  Data

  * Description of Model 1 Accuracy, Precision, and Recall scores.

  * Balanced Accuracy Score:  0.9520479254722232 

  * Confusion Matrix:
      [[18663   102]
      [   56   563]]
 
   * Classification Report:
                          
                         pre       rec       spe        f1       geo       iba       sup

                0       1.00      0.99      0.91      1.00      0.95      0.91     18765
                1       0.85      0.91      0.99      0.88      0.95      0.90       619

               avg / total       0.99      0.99      0.91      0.99      0.95      0.91     19384


* Machine Learning Model 2: Logistic Regression Model using the RandomOverSampler to reample the date Orignal Data

  * Balanced Accuracy Score: 0.9936781215845847

  * Confusion Matrix:
  [[18649   116]
  [    4   615]]
  
 
  * Classification Report
  * 
                      pre       rec       spe        f1       geo       iba       sup

            0       1.00      0.99      0.99      1.00      0.99      0.99     18765
            1       0.84      0.99      0.99      0.91      0.99      0.99       619

            avg / total       0.99      0.99      0.99      0.99      0.99      0.99     19384


## Summary

If you do not recommend any of the models, please justify your reasoning.

Both models performed very simmilar. The model with the original data set had a accurancy score of 95% vs 99% of the oversampled data. In both models the percison for the for the healthly '0'loans have a value of 1 and the risky loans '1' were 85% vs 84% respectively.

The recall is where the model differeniate themselves. Since recall measures the number of actually risky loans that the model correctly classified as risky. The recall on the both models both have a 99% of the healthy loans were projected as healthy and actually were. 

However, the recall from the model for the risky loans in the original data set have a value of 91% while the coresponding recall for the model with the resampled data is 99%.  This means the model that used the original data reflects an 8% differece in corrrecly predicting loans that are risk as being risky than the model using oversampled data.

This fact makes the model using the oversampled data a better model. This would be significant factor for any lending institution.

