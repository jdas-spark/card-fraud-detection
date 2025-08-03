**Credit Card Fraud Detection**
Detecting credit card fraud using supervised machine learning algorithms

This notebook tries out several classification techniques, including:

- KNN
- Decision Tree
- Random Forest
- XGBoost Classifier

In order to classify a dataset of transactions as either fraudulent or real. The dataset used in training the model is a synthetic dataset that has generated a more balanced number of fraudulent and real transactions, as the original dataset only has 492 fraudulent transactions out of over 200k+ total transaction records.

### Results
The results of the classification found that for the synthetic dataset, the classification models worked well (in particular, XGBoost, which was taken to be the chosen model). However, when applied to the real dataset that only contains 492 fraudulent transactions, the classification model had poor accuracy overall due to a very high false positive rate.

#### KNN Classification Results
Accuracy is  : 58.0800%
Precision is : 64.6869%
Recall is    : 66.6667%

#### Decision Tree Classification Results
Accuracy is  : 55.2400%
Precision is : 62.6316%
Recall is    : 63.3400%

#### Random Forest Classification Results
Accuracy is  : 60.6800%
Precision is : 63.9935%
Recall is    : 79.1084%

#### XGBoost Classification Results
Accuracy is  : 60.8000%
Precision is : 66.0923%
Recall is    : 71.4571%

<img width="787" height="192" alt="image" src="https://github.com/user-attachments/assets/d5433ce6-5843-4b58-b0a8-d2c82ca1d56e" />

### Conclusions
We can see from the results of the model when it uses the real credit card fraud dataset, that while it does manage to get the 492 fraudulent transactions classified as fraud (recall = 1), it ends up also classifying most of the real transactions as fraud too (precision = 0.001). This high false positive rate ends up reducing the overall accuracy as well as the area under precision-recall curve (AUPRC). 

The model works quite well for its own training and testing dataset, giving an accuracy of almost 96-97% consistently across 10 cross-validation folds. However, it does not seem to be generalisable to the real credit card fraud dataset. Further improvement is needed for this model to become better at differentiating between real and fraudulent transactions from the original dataset, as it currently incorrectly flags most of the data as fraudulent. This would be unsuitable for the use case in flagging fraudulent transactions as it would incorrectly alert credit card holders for most of their regular transactions. 

### Further Work
Potential further work for this project could include:
*   Use better computational resources to improve hyperparameter optimisation (e.g. potentially using cloud computing). This would allow the ability to use GridSearch as well instead of only RandomSearch, which is limited as it only tries a few combinations of hyperparamters at random.
*   Use/incorporate original dataset with synthetic dataset to create model. 
  * Use techniques to handle imbalance datasets, such as SMOTE/SMOTEENN and create models using the original dataset.
* Use sklearn Pipeline to test models instead of creating them individually to improve efficiency.
