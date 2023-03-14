# Liver-Disease-Prediction 
This project is centered on creating forecast models to predict liver disease.

## Dataset and Algorithm
The dataset contains 199 records and 11 independent variables including *Total Bilirubin*, *Direct Bilirubin*, *Alkphos Alkaline Phsophatase*,
*Sgpt Alanine Aminotransferase*, *Sgot Aspartate Aminotransferase*, *Total Proteins*, *Albumin*, *Albumin and Globulin Ratio (A/G Ratio)*.

**Dependent Variable**

**Class** - 1 (Liver disease) and 2 (no liver disease)

Based on the metrics and associated assumptions, one of the below algorithms will be recommended, including
* Naive Bayes.
- Logistic Regression.
+ Neural Network.

Once selected, possible improvements will be made to increase the usability of the model.

## Analysis
### Correlation Heatmap
* **The highly (positive) correlated variables**: *Albumin* was highly correlated with more than one feature (*A/G Ratio* and *Total Proteins* at *0.79* and *0.77* respectively)
* **The lowly correlated variables** : *A/G Ratio* has the least correlation with *Alkphos* and *Direct Bilirubin* at *-0.3* and *-0.28* respectively

### Pair plot
* No two independent variables helped separate the dataset to predict the output variable.
+ The pair plot showed that the values of the independent variables were close to each other, hence the overlapping, which made it difficult to determine the important features.

### Classification Report Insights

The support showed the dataset was **imbalanced**, hence **f1 score** was the first metric to be considered in determining the viability of the model.

#### Naive Bayes
+ According to the **f1 score**, the model performs poorly in predicting if there is a liver disease or not.
- The **recall** showed that the ratio of correctly predicted positive observations to all observations was accurate at 100% when there is **no liver disease** *i.e. class = 2*, however, it cannot predict when there is a liver disease.
* Similarly, the **precision** showed the model will *only* accurately predict when there is a liver disease *i.e. class = 1*
* Overall, the Naive Bayes model does poorly with respect to the weighted average.

#### Logistic Regression
By *weighted avg* (67%), this model performs better than Naive Bayes. 
* **F1 score**: The model can predict when class = 1 at 84%, which is very high. However, it will do a very poor job at predicting when class = 2 at 15%.
+ **Recall**: The recall for when *class = 1* is the highest among the three(3) metrics at 93%. This shows that the model will predict class=1 accurately, however, it cannot predict when *class = 2* (10%).
- **Precision**: The model will predict when *class = 1* better than it predicts when *class = 2* at (76% and 33%) respectively.
* Overall, across the 3 metrics, the logistic regression model does poorly at predicting class = 2 at very low percentages.

#### Neural Network (NN)
By *weighted avg* (76%), this model performs better than both Naive Bayes and Logistic Regression
* **F1 score**: This shows that NN can predict class =1 more accurately than class =2 at 83% and 55% respectively.
+ **Recall**:Like the f1 score, the recall tells us that the model can predict class =1 at 80% which is better than its performance in predicting when class =2  at 60%. 

*Interestingly, the recall of this model is the best metric to predict when class = 2 among the three models.*
- **Precision**: This shows that the model will predict class =1 at a high percentage of 86%, whereas it will predict class =2 at a lower percentage of 50%.

## Reommmendation and Justification
I recommend the **Neural Network** for the following reasons
* The metrics (i.e., the F1 score, Recall, and Precision) show that it will perform better at predicting liver disease (class =1 and class =2)
+ It is unaffected by correlation, unlike logistical regression which assumes little to no multicollinearity.
- The confusion matrix also shows that with respect to the precision and recall metrics, the Neural Network model also classifies more records accurately, than the others.

## Proposed ways to improve the chosen model
+ Consider changing the weight optimization (from “adam” to “lbfgs”) to suit the size of the data. “lbgs” works well for smaller datasets. 
* Tune the algorithm by increasing the hidden layers to help transform the input variables and provide a better output since it is different to separate the output (liver disease, or no liver disease). 














