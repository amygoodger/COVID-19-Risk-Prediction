# COVID-19 Risk Prediction: A Comparative Analysis of Machine Learning Models

## Overview
This study explores the effectiveness of different machine learning models in predicting COVID-19 positivity based on demographic and behavioral data. Three models were used: Decision Tree, Logistic Regression, and Neural Networks, each evaluated in both default settings and fine-tuned using GridSearchCV for optimal performance. The models were assessed based on accuracy, precision, recall, F1-score, and ROC curve to determine their predictive capabilities.

## Decision Tree
### Pre-processing
- Missing values in Income and Health_Condition were imputed using the median and mode, respectively.
- Categorical variables like Gender were one-hot encoded, while ordinal features like Age Group were label-encoded.
- Continuous features (Height, Weight) were standardized using StandardScaler.
- To address class imbalance, SMOTE (Synthetic Minority Over-sampling Technique) was applied.

### Model Comparison 
**Default Model:**
- Achieved 82% accuracy with overfitting observed (higher training accuracy than test accuracy).
- Important features: Age Group, Health Condition, and Income.
- Prone to overfitting due to deep trees.

**Fine-tuned with GridSearchCV:**
- Optimized max_depth, min_samples_split, and criterion to reduce overfitting.
- Accuracy improved to 84%, and generalization to new data was better.
- Reduced variance between training and testing performance.

## Regression
### Pre-processing
- Similar pre-processing as the Decision Tree.
- Standardization of numerical features was critical to ensure stable performance.
- Class imbalance handling was tested both with and without SMOTE to evaluate its effect on recall.
### Model Comparison 
**Default Model:**
- Accuracy: 84%
- Precision: 0.80, Recall: 0.72 → Some positive cases were missed.
- Simple and interpretable but struggled with recall.

**Fine-tuned with GridSearchCV:**
- Regularization parameter C and solver type were optimized.
- Recall improved to 0.78, making the model more balanced in detecting positive cases.
- Overall accuracy remained at 84%, but false negatives were reduced.

## Neural Networks
### Pre-processing
- Data was normalized to improve convergence speed.
- A Multi-Layer Perceptron (MLP) model was implemented with two hidden layers.
- Dropout layers were added to prevent overfitting.
- Early stopping was used during training to ensure optimal performance without unnecessary training cycles.
### Model Comparison 
**Default Model:**
- Accuracy: 86%, F1-score: 0.85
- Best overall performance but required significant computational power.
- Less interpretable compared to Decision Tree and Logistic Regression.

**Fine-tuned with GridSearchCV:**
- Hyperparameters like hidden_layer_sizes, learning_rate, and alpha were optimized.
- Achieved the highest ROC-AUC (0.90) and recall (0.81), making it the best-performing model.
- Despite improvements, it remained a "black-box" model with limited interpretability.

## Decision-Making 
### Strenghts
- The Neural Network demonstrated the highest overall performance, particularly in recall and F1-score, making it the most effective model for accurate predictions.
- The Decision Tree provided strong interpretability, offering clear insights into key factors influencing COVID-19 positivity.
- Logistic Regression was computationally efficient and performed well with hyperparameter tuning, making it a viable choice for rapid analysis.
### Limitations:
- The Decision Tree exhibited overfitting in its default configuration, necessitating pruning and fine-tuning to enhance generalization.
- Logistic Regression struggled with recall, which may result in a higher number of false negatives and limit its effectiveness in identifying positive COVID-19 cases.
- Neural Networks required extensive hyperparameter tuning and lacked interpretability, making them less suitable for decision-making in contexts where model transparency is essential.
## Final Recommendation
- If predictive accuracy and performance are the top priorities, the Neural Network is the most suitable choice.
- If interpretability and explainability are critical, the Decision Tree offers valuable insights.
- If a computationally efficient and interpretable model with reasonable accuracy is required, Logistic Regression provides a balanced option.


































