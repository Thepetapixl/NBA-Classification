# NBA Player Position Classification

## Problem Statement

The objective of this project is to classify NBA players into five positions on the basketball court based on their per-game average performance during the 2020-2021 season. The positions to classify are:
- SG (Shooting Guard)
- PG (Point Guard)
- SF (Small Forward)
- PF (Power Forward)
- C (Center)

The dataset provided for this task, "NBAstats.csv", includes various statistics for each player. The task involves implementing a classification method to accurately predict the positions.

## Methodology

### Data Preparation

The dataset "NBAstats.csv" was loaded using pandas. Relevant features were selected to train the classification model. No preprocessing was done on the data as the initial accuracy was satisfactory.

### Model Implementation

An SVM (Support Vector Machine) classifier with a linear kernel was chosen for this task. The dataset was split into training (75%) and testing (25%) sets to evaluate the model's performance.

### Model Evaluation

The accuracy of the model was calculated using the test set, and a confusion matrix was generated to visualize the performance across all classes.

### Cross-Validation

To further validate the model, 10-fold stratified cross-validation was performed using the same model and parameters.

## Results

### Initial Model Evaluation

- **Accuracy**: The accuracy of the SVM model with a linear kernel on the test set was approximately 53%.
- **Confusion Matrix**: The confusion matrix for the model is as follows:
[[TP_SG, FP_PG, FP_SF, FP_PF, FP_C],
[FP_SG, TP_PG, FP_SF, FP_PF, FP_C],
[FP_SG, FP_PG, TP_SF, FP_PF, FP_C],
[FP_SG, FP_PG, FP_SF, TP_PF, FP_C],
[FP_SG, FP_PG, FP_SF, FP_PF, TP_C]]


### Cross-Validation Results

- **Cross-validation Accuracies**: The accuracies for each fold during the 10-fold stratified cross-validation were recorded.
- **Average Accuracy**: The average accuracy across all folds was also around 53%.

## Discussion

### Method and Observations

The approach to achieve better accuracy included understanding the game and positions better through research and surveys. Key observations included:

- Percentages (like 3-point percentage) can be misleading with small sample sizes.
- Direct preprocessing was not necessary as the raw data provided good initial results.
- Weighting categories for position classes might lead to overfitting.

The SVM classifier with a linear kernel was selected based on its performance. Despite various attempts to improve accuracy by tweaking feature sets and model parameters, the highest accuracy achieved was around 53%.

## Conclusion

In this project, we successfully classified NBA players into their respective positions using an SVM classifier. While the accuracy achieved was modest, the process provided valuable insights into the factors influencing player classification. Future work could explore additional preprocessing steps and alternative models to further enhance performance.

