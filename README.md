# Advancing Fraud Detection: Machine Learning in Digital Transactions

## Table of Contents

* [Introduction](#introduction)
* [Dataset](#dataset)
* [Methodology](#methodology)
    * [Data Preparation and Preprocessing](#data-preparation-and-preprocessing)
    * [Model Development and Evaluation](#model-development-and-evaluation)
    * [Insights and Recommendations](#insights-and-recommendations)
* [Results](#results)
* [Future Work](#future-work)
* [License](#license)
* [Contact](#contact)
* [Acknowledgments](#acknowledgments)

## Introduction

In the escalating battle against financial fraud, advanced analytics and machine learning emerge as indispensable tools for enhancing the security of digital financial activities. This project leverages machine learning to detect and predict fraudulent credit card transactions, enhancing the security of digital financial activities. This project analyzes a simulated dataset provided by Capital One, encompassing 786,363 transactions with 29 attributes. Through rigorous data preprocessing, model development (including various ML algorithms and resampling techniques), and comprehensive evaluation, we aim to deliver actionable insights and strategic recommendations to bolster fraud detection mechanisms.

## Dataset

The [Capital One dataset] (https://github.com/CapitalOneRecruiting/DS) simulates real-world transactional dynamics, providing a valuable testing ground for fraud detection algorithms. It comprises:

* **Transactions:** 786,363
* **Attributes:** 29 (including transaction amount, merchant details, dates, types, and security attributes like CVV matches)

**Challenges:**

* **Class Imbalance:** Fraudulent transactions are significantly less frequent than legitimate ones.
* **Missing Data:** Some attributes contain missing values.

## Methodology

### Data Preparation and Preprocessing

* **Data Cleaning:** Removal of duplicate transactions (reversals, multi-swipes) and irrelevant columns.
* **Missing Value Imputation:** Strategic imputation for missing values in categorical and numerical columns.
* **Feature Engineering:** Creation of time-based features and one-hot encoding of categorical variables.
* **Standardization:** Scaling of numerical features to ensure consistency.

### Model Development and Evaluation

* **Class Imbalance Handling:** Oversampling (SMOTE) and undersampling techniques explored. **Undersampling proved most effective, improving recall from 0.07 to 0.70.**
* **Model Selection:** Logistic regression, Random Forest, and XGBoost models evaluated. **Logistic regression chosen for further refinement.**
* **Feature Selection (RFE):** Recursive feature elimination to identify the most impactful features. **12 key features selected, boosting recall to 0.79.**
* **Hyperparameter Tuning:** Optimization of regularization parameters for the logistic regression model. **Elastic Net with l1 ratio of 0.95 and C of 0.1 ensured model stability.**
* **Threshold Optimization:** Adjustment of decision threshold to 0.4. **Final recall achieved: 0.89.**

### Insights and Recommendations

* **High-Risk Categories:** Airlines, online retail, rideshare, and unknown merchant countries.
* **Protective Factors:** Fuel, mobile apps, online subscriptions, food delivery, POS Entry Mode 05, address verification.
* **Transaction Amount:**  Higher transaction amounts are more likely to be fraudulent. 
* **Time-Based Patterns:** Fraudulent transactions tend to occur at specific times and days.

**Strategic Recommendations:**

* **Targeted Monitoring:** Implement specialized monitoring for high-risk categories, focusing on real-time data analysis and anomaly detection.
* **Adaptive Systems:** Develop fraud detection systems that dynamically adjust based on transaction risk profiles, incorporating real-time assessments and historical data.
* **Enhanced Security:** Promote secure transaction methods (chip-enabled POS, address verification) and educate stakeholders on their importance.
* **Dynamic Thresholds:** Continuously fine-tune detection thresholds based on ongoing data analysis.
* **Collaboration:** Foster collaboration among stakeholders to share insights and develop comprehensive security strategies.

## Results 

* **Final Model:** The logistic regression model with undersampling, selected features, regularization, and optimized threshold achieved the best performance.
* **Performance Metrics:** Detailed classification reports and visualizations are available in the project notebook.
* **Economic Impact:** The model successfully identified approximately $748,348 in fraudulent transactions.

## Future Work

* **Explore additional models:** Experiment with other machine learning algorithms or ensemble methods.
* **Incorporate more data:** Integrate additional data sources (e.g., customer demographics, location data) for enhanced predictive power.
* **Real-time Detection:** Implement a real-time fraud detection system.

## License

This project is licensed under the MIT License.

## Contact

This analysis was conducted by Jasmine Kuo, a data scientist with a passion for leveraging analytics to address global challenges. For inquiries or collaboration, reach out via [Email](mailto:ik2437@nyu.edu) or [LinkedIn](https://www.linkedin.com/in/jasmineejkuo/).

## Acknowledgments

* Capital One for providing the simulated transaction dataset.
