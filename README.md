# Promotion_Predictor

# Calculated various accuracy metrics for predicting whether an employee would get promoted 

Project Overview:

This document provides insights into the Employee Promotion Prediction Machine Learning (ML) project, highlighting key observations and decisions made during data preprocessing, transformation, and model evaluation.

Handling Null Values:

Three columns exhibited a substantial number of null values.
To address missing values in the "previous_year_rating" column, an assumption was made that it might be related to the "no_of_trainings" column. However, it's essential to note that correlation does not imply causation.
The choice to use "no_of_trainings" was based on an educated guess and appeared more reasonable than other columns.
Null values in the "avg_training_score" column were imputed using "previous_year_rating" and "awards_won" based on correlation and intuition.

Data Distribution Analysis:

A Q-Q (Quantile-Quantile) plot was employed to assess the distribution of data points.
Normally distributed data points typically align in a straight line on the Q-Q plot.
Three columns were identified as having skewed data, indicating the need for log transformation to normalize the data.
The "age" column exhibited numerous outliers, as observed from box plots.

Data Transformation and Scaling:

Data transformation is a valuable technique for addressing highly skewed datasets.
Transformation methods, such as natural log, can reduce the impact of extreme values and improve data distribution.
Scaling data is a critical step in ML data preparation, ensuring that data points are comparable and preventing bias in analyses.
Scaling brings distant data points closer, enhancing algorithm effectiveness and processing speed.

Model Evaluation:

The Area Under the ROC Curve (AUC) was not calculated for the Support Vector Machine (SVM) model due to SVM's inability to compute probabilities, which are necessary for AUC calculation.
Parameter fine-tuning for SVM was attempted but later removed due to the excessive time required. GridSearchCV is computationally expensive, particularly with a large number of parameter combinations.

Evaluation Metrics:

Different evaluation metrics were used to assess model performance:

Precision (TP/(TP+FP))

Accuracy ((TP+TN)/(TP+TN+FP+FN)): Measures the fraction of correct predictions.

Recall (TP/(TP+FN))

F1 Score (Harmonic Mean of Precision and Recall): Particularly useful when minimizing both False Negatives and False Positives is essential.

ROC Curve: Plots Sensitivity against False Positive Rate, with AUC indicating model performance. A higher AUC signifies a better model.

Conclusion:

This ML project involved meticulous data preprocessing, transformation, and model evaluation. The decision-making process encompassed handling null values, assessing data distribution, transforming data, and employing diverse evaluation metrics. The project's outcomes and insights contribute to better decision-making in employee promotion predictions.
