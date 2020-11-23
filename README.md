# Credit_Risk_Analysis

## Analysis Overview
In this project, we use Python to build and evaluate several machine learning models to predict credit risk.\
We adopted the following procedure:
- oversample the data using the **RandomOverSampler** and **SMOTE** algorithms.
- Undersample the data using the **ClusterCentroids** algorithm.
- Use a combinatorial approach of over- and undersampling using the **SMOTEENN** algorithm.
- Compare two machine learning models that reduce bias, **BalancedRandomForestClassifier** and **EasyEnsembleClassifier**.

We will evaluate the performance of these models and make a recommendation on whether they should be used to predict credit risk.

## Resources
- Data Source: LoanStats_2019Q1.csv
- Software: Python 3.7.9, Anaconda Navigator 1.9.12, Conda 4.8.4, Jupyter Notebook 6.0.3

## Results (Balanced Accuracy Scores, Confusion Matrixes and Imbalanced Classification Reports)

### RandomOverSampler model
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/99927593-783bb080-2d0b-11eb-8dda-30917e42c517.png"><img src="https://user-images.githubusercontent.com/68669675/99927595-78d44700-2d0b-11eb-891f-2dd0b308f312.png"><img src="https://user-images.githubusercontent.com/68669675/99927597-796cdd80-2d0b-11eb-81f0-d71ecd340724.png">
</p>
The balanced accuracy score is 65%.<br>The high_risk precision is about 1% only with 62% sensitivity which makes a F1 of 2% only.<br>Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 68%.
<br><br>

### SMOTE model
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/99928062-327fe780-2d0d-11eb-9789-3b50bce5822c.png"><br><img src="https://user-images.githubusercontent.com/68669675/99928063-33187e00-2d0d-11eb-8d86-e61bc3d1df73.png"><img src="https://user-images.githubusercontent.com/68669675/99928064-33b11480-2d0d-11eb-97d5-f35aa12a2ad9.png">
</p>
The results are pretty similar to the previous model.<br>The balanced accuracy score is 64%.<br>The high_risk precision is about 1% only with 63% sensitivity which makes a F1 of 2% only.<br>Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 66%.
<br><br>

### ClusterCentroids model
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/99928471-e8980100-2d0e-11eb-81fa-343e9a2f2b4c.png"><br><img src="https://user-images.githubusercontent.com/68669675/99928472-e9309780-2d0e-11eb-95dd-697a356b8720.png"><img src="https://user-images.githubusercontent.com/68669675/99928475-e9309780-2d0e-11eb-9cb1-5bb5497a7e93.png">
</p>
Here the balanced accuracy score is down to about 52%.<br>The high_risk precision is still 1% only with 63% sensitivity which makes a F1 of 1%.<br>Due to the high number of false positives, the low_risk sensitivity is only 40%.
<br><br>

### SMOTEENN model
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/99928917-d15a1300-2d10-11eb-9b0b-ca9fc4d9d51b.png"><br><img src="https://user-images.githubusercontent.com/68669675/99928919-d1f2a980-2d10-11eb-84ea-3925e5ce28bb.png"><img src="https://user-images.githubusercontent.com/68669675/99928920-d1f2a980-2d10-11eb-9836-51dfff33a7fb.png">
</p>
The balanced accuracy score is about 62%.<br>The high_risk precision is still 1% only with 68% sensitivity which makes a F1 of only 2%.<br>Due to the high number of false positives, the low_risk sensitivity is 57%.
<br><br>

### BalancedRandomForestClassifier model
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/99929395-b8526180-2d12-11eb-9108-755b970e0610.png"><img src="https://user-images.githubusercontent.com/68669675/99929396-b8eaf800-2d12-11eb-841c-7d5b902243ad.png"><img src="https://user-images.githubusercontent.com/68669675/99929398-b9838e80-2d12-11eb-9727-ea4f9d33374c.png">
</p>
The balanced accuracy score improved to about 79%.<br>The high_risk precision is still low at 4% only with 67% sensitivity which makes a F1 of only 7%.<br>Due to a lower number of false positives, the low_risk sensitivity is now 91% with 100% presicion.
<br><br>

### EasyEnsembleClassifier model
<p align="center">
  <img src="https://user-images.githubusercontent.com/68669675/99929696-c5238500-2d13-11eb-9257-54bc815da0b0.png"><br><img src="https://user-images.githubusercontent.com/68669675/99929697-c5bc1b80-2d13-11eb-82c9-85c19344397a.png"><img src="https://user-images.githubusercontent.com/68669675/99929698-c5bc1b80-2d13-11eb-90ee-e20d9994b95d.png">
</p>
Now, the balanced accuracy score is high to about 93%.<br>The high_risk precision is still low at 7% only with 91% sensitivity which makes a F1 of only 14%.<br>Due to a lower number of false positives, the low_risk sensitivity is now 94% with 100% presicion.
<br><br>

## Summary
All the models used to perform the credit risk analysis show weak precision in determining if a credit risk is high.\
The Ensemble models brought a lot more improvment specially on the sensitivity of the high risk credits.\
The EasyEnsembleClassifier model shows a recall of 92% so it detects almost all high risk credit. On another hand, with a low precision, a lot of low risk credits are still falsely detected as high risk which would penalize the bank's credit strategy and infer on its revenue by missing those business opportunities.\
For those reasons I would not recommend the bank to use any of these models to predict credit risk.