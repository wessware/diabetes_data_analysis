# Type II Diabetes Mellitus classifier in pateints based on cardiovascular data

This project intends to investigate whether patients have type on their cardiovascular medical data.
The provided dataset [diabetes.csv] has 19 rows from which we will extract new features including the
target feature.

## Data Preparation

To initiate the project, we delve into understanding the provided data in so to understand the essence and needs of the business approach.
Conventional approaches for data preparation [imputation for missing values converting column data to numerical values proceed as suite].

## Feature Engineering

In order to properly model the problem at hand, it is important that we extract any usable features from the availed data to improve the performance of our predictors.

### height_meters

This feature was engineered by multiplying the 'height' column with 0.025 to convert into into meters.

### BMI

This feature was engineered by dividing the 'weight' columns with the square of the 'height_meters' column

### hip_waist_ratio

This feature was engineered by dividing the 'hip' column with the 'waist' column.

### diabetic

This feature by separating values in the 'glhb' into two categories; 0 for values below 7, and 1 for values above 7. This was target variable for our models.

## Modelling

The preprocessed was fitted on three classifier models; Support Vector Machines [svm], Random Forests [RF], and Extreme Gradient Boosting [XGB] classifier. The test-train ratio was varried by 10% in two different training cycles to investigate impact on model performance.

## Performance

The ensemble models, RF and XGB (as expected), outperform the SVM models, although all models generalize well, with each scoring a classification accuracies > 90%.

Random hyperparameter tuning for the ensemble models does allow the XGB classifier to perform better than the RF models.

Varrying the training-ratio and altering the features used to fit and train the models does have little impact on the two ensemble classifiers, it however, does significantly improve the performance of the SVM classifier.

## Evaluation

For this project several evaluation metrics are employed; Mean Absolute Error [MAE], Root Mean Squared Error [RMSE], ROC-AUC, Precision, Recall and F1-score. The models in some instances did score 100% on the Precision and Recall scores.

## Inference and Recommendation

The classifiers do perform well here, however the project does recommend fitting the models with a more elaborate data that has more instances than the current. Further tuning of the ensemble models can help elevate the importance of one over the other.
