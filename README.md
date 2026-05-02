# Researching the severity of COVID-19 based on presenting symptoms using machine learning
Project for Independent Study with Dr. Wang

Created by Sadia Rahman, Tilina Alzaben

## Dataset:
[Symptoms and COVID Presence (May 2020 data)](https://www.kaggle.com/datasets/hemanthhari/symptoms-and-covid-presence) <br>

## Overview:
This project builds and evaluates machine learning models to predict COVID-19 infection based on patient-reported symptoms and underlying health conditions. Using a publicly available Kaggle dataset, both a Decision Tree and an XGBoost model were trained to classify infection status from binary symptom indicators. The Decision Tree provides interpretable decision rules, while XGBoost delivers improved predictive performance, achieving an accuracy of 97.1%. The model demonstrates strong ability to identify positive cases with high recall, and feature importance analysis highlights key predictors such as sore throat, travel history, and contact with infected individuals. This project showcases how tree-based models can effectively balance interpretability and performance when working with structured healthcare data.

## Results:
### XGBoost Model
The XGBoost model was selected as the primary predictive model due to its ability to capture complex, non-linear relationships between symptoms and COVID-19 infection status. Unlike a single decision tree, XGBoost builds an ensemble of trees sequentially, where each new tree corrects the errors of the previous ones. This results in a more robust and accurate model, particularly well-suited for structured datasets with binary features like this one.

The final XGBoost model achieved an accuracy of 97.1%, with especially strong performance in identifying COVID-positive cases. The model reached a recall of 0.99 for the positive class, meaning it correctly identified nearly all infected individuals while minimizing false negatives. This is critical in a health-related context, where missing a positive case can have significant consequences.

The confusion matrix further reinforces this performance, showing a high number of true positives (871) and a very low number of false negatives (6). While the model produces a small number of false positives (26), this tradeoff is acceptable given the priority of detecting positive cases. Overall, the results demonstrate that XGBoost provides a strong balance of accuracy, sensitivity, and reliability for this classification task.
<img width="521" height="451" alt="image" src="https://github.com/user-attachments/assets/9db9fae0-96bc-4e72-b95d-7571d6675d5f" />

### Decision Tree Model
A Decision Tree classifier was implemented as a baseline model to provide interpretability and insight into how individual features contribute to predictions. Unlike XGBoost, which combines multiple trees, the Decision Tree uses a single tree structure to split the data based on feature values, making it easy to visualize and understand the decision-making process.

The Decision Tree achieved an accuracy of 96.3%, which is slightly lower than XGBoost but still demonstrates strong performance. The model effectively captures key decision patterns in the data, using features such as sore throat, travel history, and contact with COVID-positive individuals to guide predictions.

While the Decision Tree performs well, it is more prone to overfitting and less capable of capturing complex interactions between features compared to XGBoost. However, its interpretability makes it valuable for understanding how specific symptoms and conditions influence predictions, providing transparency that more complex models lack.
<img width="1094" height="547" alt="image" src="https://github.com/user-attachments/assets/1be93713-f6b3-4f0c-893b-73bcc8bf43ff" />

### Comparison
Both models performed well on this classification task, but they offer different strengths. The Decision Tree provides clear and interpretable decision rules, making it useful for understanding how individual features influence predictions. In contrast, XGBoost delivers higher predictive performance by combining multiple trees and capturing more complex relationships within the data.

In terms of accuracy, XGBoost slightly outperforms the Decision Tree (97.1% vs. 96.3%), and it demonstrates superior recall for COVID-positive cases, making it more effective at minimizing false negatives. This makes XGBoost the preferred model for prediction, particularly in scenarios where detecting positive cases is critical.

## Conclusion
Overall, the XGBoost model emerged as the better-performing approach, achieving higher accuracy (97.1%) and stronger recall for COVID-positive cases compared to the Decision Tree. Its ability to capture more complex relationships between symptoms and infection status allows it to make more reliable predictions, particularly in minimizing false negatives. Given the importance of correctly identifying positive cases in a health context, XGBoost is the preferred model for this task.

Feature importance analysis revealed that symptoms and exposure-related factors such as sore throat, abroad travel, breathing problems, and contact with COVID-positive individuals had the greatest influence on predictions. These findings align with expected real-world indicators of infection risk, suggesting that both symptom severity and exposure history play a critical role in determining outcomes.
