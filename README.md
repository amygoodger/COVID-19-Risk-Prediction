# COVID-19 Risk Prediction: A Comparative Analysis of Machine Learning Models

## Overview
This study explores the effectiveness of different machine learning models in predicting positive cases of COVID-19 based on demographic and behavioural data. Three models were compared: Decision Tree, Logistic Regression, and Neural Networks. The performance of all models was initially assessed to determine the best-performing model for each machine learning model. All models were assessed based on their deafult settings, then fine-tuned using GridSearchCV, with Logistic Regression also undergoing dimensionality reduction and Neural Networks applying feature selection. The models were evaluatedd based on accuracy, precision, recall, F1-score, and ROC curve. 

## Performance Comparison
The precision, recall, F1-score, and accuracy of the best models for each machine learning algorithm are shown below, along with the ROC curve comparing all models.

**Decision Tree:**

![image](https://github.com/user-attachments/assets/b01654dc-a35e-46d4-9b04-a0725e7a488b)

**Regression:**

![image](https://github.com/user-attachments/assets/c41ae9a7-ed19-41d7-b4cd-1a098c19db90)

**Neural Network:**

![image](https://github.com/user-attachments/assets/9166aa9f-c7cb-4dec-bc82-89882b4fef97)

**ROC Curve:**

![image](https://github.com/user-attachments/assets/e53f44f6-6bbf-4335-9b33-37a8ce282b7a)

### Key Insights:
- Neural Network outperformed both Decision Tree and Regression models across all metrics.
- While Regression showed no signs of overfitting, it had the worst predictive performance.
- The Decision Tree model was interpretable but prone to overfitting.
- The Neural Network had the highest testing accuracy and the largest area under the ROC curve, making it the best model for decision-making.

## Positives & Negatives of Each Predictive Modelling Method

### **Decision Tree**
**Positives:**
- Testing accuracy was slightly higher than regression.
- Model structure is interpretable, aiding in variable importance analysis.
- Useful for feature selection in training more advanced models.

**Negatives:**
- Lowest area under the ROC curve.
- High risk of overfitting, with training accuracy significantly higher than testing accuracy.

### **Regression**
**Positives:**
- No major signs of overfitting (training accuracy < testing accuracy).
- Better ROC performance than Decision Tree, but not as strong as Neural Network.

**Negatives:**
- Worst performer in precision, recall, F1-score, and accuracy.
- Model coefficients provide some interpretability but are less descriptive than a Decision Tree.

### **Neural Network**
**Positives:**
- Best performing model across all key metrics.
- Chosen for final decision-making due to superior precision, recall, and AUC-ROC.

**Negatives:**
- Black-box nature makes variable interpretation difficult.
- Higher computational cost: Training times are significantly longer.
- Hyperparameter tuning challenges: Grid search can take over 5 minutes, and may become infeasible for large datasets.

## Conclusion
The Neural Network model provides the best balance of predictive power and reliability, making it the ideal choice for COVID-19 prediction. While interpretability and computational cost remain challenges, the superior accuracy and robustness outweigh these drawbacks for this case study.

**Areas for further improvement:**
- Further optimisation of hyperparameters to reduce training time.
- Exploration of explainability techniques (e.g., SHAP values) to interpret model predictions.
- Deployment of the model into a real-world application for automated predictions.









