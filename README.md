Credit Card Fraud Detection using Logistic Regression

Overview

This project aims to develop a machine learning model that can accurately detect fraudulent credit card transactions. Credit card fraud is a significant problem, resulting in billions of dollars in losses each year. This project explores the use of Logistic Regression to identify fraudulent transactions in a real-time setting, enabling timely intervention and minimizing financial losses.

Problem Statement

Credit card fraud is a growing concern for both consumers and financial institutions. The ability to quickly and accurately identify fraudulent transactions is crucial for preventing financial losses and protecting consumers from unauthorized charges. Traditional rule-based systems for fraud detection are often limited in their ability to detect new and sophisticated fraud schemes. This project addresses this challenge by developing a machine learning model that can learn complex patterns in transaction data and identify fraudulent transactions with high accuracy.

Data

The dataset used in this project is the "Credit Card Fraud Detection" dataset from Kaggle, originally created and shared by Andrea Dal Pozzolo, Olivier Caelen, Reid A. Johnson and Gianluca Bontempi. The dataset contains transactions made by credit cards in September 2013 by European cardholders. Due to confidentiality constraints, the original features have been transformed using Principal Component Analysis (PCA), resulting in 28 anonymized features (V1-V28). The dataset also includes the transaction `Time`, the `Amount`, and a `Class` label indicating whether the transaction is fraudulent (1) or not (0).
     

Key characteristics:

Anonymized Features: The PCA transformation makes it difficult to interpret the individual features, but it preserves the underlying relationships in the data.
Class Imbalance: The dataset is highly imbalanced, with fraudulent transactions representing only a small fraction of the total number of transactions. This requires special consideration when training and evaluating the model.
     

Methods

This project employed the following methods:

1.  Data Preprocessing:
    Undersampling: To address the class imbalance, the majority class (non-fraudulent transactions) was undersampled to create a more balanced dataset.
    Feature Scaling: The `Time` and `Amount` features were scaled using `StandardScaler` to ensure that all features are on the same scale and to prevent features with larger values from dominating the model.
2.  Model Selection:
    Logistic Regression was chosen as the primary model due to its simplicity, interpretability, and ability to handle binary classification problems.
    Random Forest and XGBoost were also explored as alternative models.
3.  Model Training:
    The Logistic Regression model was trained on the preprocessed data using the `fit` method.
4.  Model Evaluation:
    The performance of the model was evaluated using precision, recall, F1-score, and the Area Under the Precision-Recall Curve (AUPRC).
    A confusion matrix was used to visualize the model's performance in terms of true positives, true negatives, false positives, and false negatives.
5.  Threshold Tuning:
    The probability threshold for classifying transactions as fraudulent was tuned to optimize the balance between precision and recall.
6.  Simulation:
    A simulation was created to mimic real-time transactions that were more likely to be fraudulent during certain times of the day.

Results

The Logistic Regression model achieved the following results:

Precision: TP / (TP + FP) = 102 / (102 + 7) = 102 / 109 = 0.936

Recall: TP / (TP + FN) = 102 / (102 + 8) = 102 / 110 = 0.927

F1-Score: 2 * (Precision * Recall) / (Precision + Recall) = 2 * (0.936 * 0.927) / (0.936 + 0.927) = 1.735 / 1.863 = 0.931

AUPRC: 0.908


The Random Forest and XGBoost models achieved comparable performance.

Output for Random Forest model:

Precision : TP / (TP + FP) = 98 / (98 + 3) = 98 / 101 = 0.970

Recall : TP / (TP + FN) = 98 / (98 + 12) = 98 / 110 = 0.891

Output for XGBoost model:

Precision : TP / (TP + FP) = 101 / (101 + 4) = 101 / 105 = 0.962

Recall : TP / (TP + FN) = 101 / (101 + 9) = 101 / 110 = 0.918
     

Insights

#This project demonstrated the effectiveness of Logistic Regression for credit card fraud detection, even with anonymized features. The importance of addressing class imbalance was highlighted through the use of undersampling. The threshold tuning step further improved the model's performance by allowing us to optimize the balance between precision and recall based on the specific needs of the application. The generated time transactions also allowed more realistic simulation of fraudulent behavior.

Conclusion

This project successfully developed a machine learning model that can accurately detect fraudulent credit card transactions. The model can be used to identify fraudulent transactions in real-time, enabling timely intervention and minimizing financial losses. The project also highlighted the importance of data preprocessing, model selection, and threshold tuning in achieving optimal performance.
     

Future Work

Potential directions for future work include:

Feature Engineering: Explore new features that could improve the model's ability to discriminate between fraudulent and non-fraudulent transactions.
Real-Time Data Integration: Integrate the model with a real-time data stream from a payment processor to simulate a production environment.
Deployment: Deploy the model to a cloud platform (e.g., AWS, Azure, Google Cloud) to make it accessible to a wider audience.
Explore other fraud methods: There are always new fraud methods appearing, and this model should be continuously trained and evaluated.

Code

The code for this project is available in this repository. To run the code, you will need to have the following libraries installed:

 Pandas
 NumPy
 Scikit-learn
 Matplotlib
 Seaborn

     

Acknowledgements

I would like to thank Andrea Dal Pozzolo, Olivier Caelen, Reid A. Johnson and Gianluca Bontempi, Worldline, and the Machine Learning Group(http://mlg.ulb.ac.be)
of ULB (Université Libre de Bruxelles) for creating and sharing the Credit Card Fraud Detection dataset on Kaggle. Their work has made this project possible.
