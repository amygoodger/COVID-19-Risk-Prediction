# COVID-19 Risk Prediction: A Comparative Analysis of Machine Learning Models

## Overview
This study explored the effectiveness of different machine learning models in predicting positive COVID-19 cases based on demographic and behavioural data. The performance of decision trees, logistic regression, and neural networks were compared to determine the best-performing model. Each model was first evaluated using its default settings and then fine-tuned using GridSearchCV. Additionally, logistic regression underwent dimensionality reduction, while neural networks applied feature selection to enhance performance. The models were assessed based on key evaluation metrics, including accuracy, precision, recall, F1-score, and the ROC curve. This approach provided a comprehensive comparison of the models, identifying the most effective technique for COVID-19 case prediction.

## Performance Comparison
For each machine learning model, the training and test accuracy, along with the classification report, are presented below. Additionally, ROC curves are provided to compare the different variations within each model category.

### Decision Tree
The fine-tuned decision tree model outperformed the default model in all key performance metrics, including accuracy, F1-score, and area under the ROC curve. Fine-tuning helped reduce overfitting by optimising the tree depth, allowing the model to generalise patterns better and improve classification performance. The default model, in contrast, learned more noise from the data, leading to lower accuracy and a less reliable decision boundary.

| Default Settings | Fine-tuned |
|---------|---------|
| ![image](https://github.com/user-attachments/assets/a32862dd-f5a3-4090-b6f5-442dee0e07bc) | ![image](https://github.com/user-attachments/assets/7d7ed74d-5add-4b11-b1ac-1a59c0603ed0) |

**ROC Curve for Decision Tree Models**

![image](https://github.com/user-attachments/assets/8a9ff857-cff3-461e-b8c5-6817bf3068f9)

### Regression
Among the three logistic regression models, the model with dimensionality reduction demonstrated the best performance. It achieved the highest Area Under the ROC Curve, indicating superior ability to distinguish between COVID-19 positive and negative cases. Additionally, it had the highest F1-score for both classes and the best testing accuracy, with no signs of overfitting.

| Default Settings | Fine-tuned | Dimensionality Reduction |
|---------|---------|---------|
| ![image](https://github.com/user-attachments/assets/ee98353e-9ea9-4c56-a3ed-3acb4cf68cf5) | ![image](https://github.com/user-attachments/assets/8cb5be5c-63b4-4d6f-95a4-8a3d86dce8e9) | ![image](https://github.com/user-attachments/assets/e820df35-5e61-4abe-9ddd-b6c724c851a0) |

**ROC Curve for Regression Models**

![image](https://github.com/user-attachments/assets/78ec7c80-96ea-49be-9a10-e0cad6d0d452)


### Neural Network
Four neural network models were compared based on their F1-scores and ROC curves. The best-performing model, Model 4 (feature-reduced, two-dimensional hidden layer architecture), achieved the highest area under the ROC curve, best F1-score for both COVID-positive and COVID-negative predictions, and highest testing accuracy with minimal signs of overfitting. These factors confirm that Model 4 is the most effective neural network model for predicting COVID-positive individuals.

While some feature importance can be inferred from input layer connections, neural networks operate as a black box, limiting interpretability. If model transparency is a priority, a more interpretable model like decision trees or logistic regression may be preferable despite lower accuracy.

| Default Settings | Default Model w/ Maximum Iterations |
|---------|---------|
| ![image](https://github.com/user-attachments/assets/11d36cfd-0bed-4e99-92c3-6349cbbbb857) | ![image](https://github.com/user-attachments/assets/72cb070e-83f4-4f8b-a826-6e3fb0a3258a) |
| **Fine-tuned** | **Reduced Feature Set**|
| ![image](https://github.com/user-attachments/assets/92528435-7772-4cb7-9569-0414b460545e)  | ![image](https://github.com/user-attachments/assets/fcb2649d-36c3-40d4-ada5-d8eec206cdba) |


**ROC Curve for Neural Network Models**

![image](https://github.com/user-attachments/assets/f1be3f3e-2eaa-4e66-94b8-3439ef321524)

### ROC Curve for Best Models
![image](https://github.com/user-attachments/assets/e53f44f6-6bbf-4335-9b33-37a8ce282b7a)

### Key Insights:
- Neural Network outperformed both Decision Tree and Regression models across all metrics.
- While Regression showed no signs of overfitting, it had the worst predictive performance.
- The Decision Tree model was interpretable but prone to overfitting.
- The Neural Network had the highest testing accuracy and the largest area under the ROC curve, making it the best model for decision-making.

## Positives & Negatives of Each Predictive Modelling Method
| Model           | Positives                                                                                                                                                  | Negatives                                                                                                                                                 |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Decision Tree** | - The testing accuracy is slightly higher than the regression model but lower than the neural network. <br><br> - The structure of the decision tree is visible and interpretable, allowing for informed decisions about individual variables, unlike more "black box" models. <br><br> - Can be used in feature selection when training other, more accurate models. | - The best decision tree has the smallest area under the ROC curve of the three models. <br><br> - It shows the most signs of overfitting with a significantly higher training accuracy compared to testing accuracy. |
| **Regression**   | - The regression model with feature selection is the only model showing no major signs of overfitting, with the training accuracy being lower than testing accuracy. <br><br> - The area under the ROC curve is better than the decision tree but not as good as the neural network. | - It is the worst performing model in terms of precision, recall, F1-score, and testing accuracy. <br><br> - While the effect of variables can be interpreted via the model coefficients, it is less descriptive than the decision tree model, making it harder to derive insights. |
| **Neural Network**| - The neural network was the best performer in terms of precision, recall, F1-score, area under the ROC curve, and both training and testing accuracies. <br><br> - It was ultimately chosen as the final model for decision making due to these factors. | - The black box nature of the hidden layers makes it difficult for a human to interpret the effect of different variables on the model’s predictions. <br><br> - Training time is significantly longer than the other models. <br><br> - A grid search over hyperparameters can take over 5 minutes, compared to less than one minute for other models, making it infeasible for larger datasets. |


## Conclusion
The Neural Network model provides the best balance of predictive power and reliability, making it the ideal choice for COVID-19 prediction. While interpretability and computational cost remain challenges, the superior accuracy and robustness outweigh these drawbacks for this case study.

**Areas for further improvement:**
- Further optimisation of hyperparameters to reduce training time.
- Exploration of explainability techniques (e.g., SHAP values) to interpret model predictions.
- Deployment of the model into a real-world application for automated predictions.









