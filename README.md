# Employee Burnout Prediction Analysis

# Project Overview

Employee burnout is a psychological process resulting from prolonged job-related stress. It manifests as emotional exhaustion, physical fatigue, and a sense of dread regarding work responsibilities. As noted by Susan E. J and Randall S. S. (1983), early detection is vital for organizational health.

This project utilizes Machine Learning to predict the Burn Rate of employees based on various factors like mental fatigue, resource allocation, and work-from-home (WFH) availability. The goal is to provide HR departments with an "early warning system" to identify at-risk employees.

# Dataset Description

The analysis is performed on two separate datasets:

Train Data: Used for exploratory data analysis (EDA), cleaning, and model training.

Test Data: Used for final validation to ensure the model generalizes to unseen data.

Key Features:

Employee ID: Unique identifier.

Date of Joining: Timestamp of employment start.

Gender: Male/Female.

Company Type: Service/Product.

WFH Setup Available: Yes/No.

Designation: Professional rank (1.0 to 5.0).

Resource Allocation: Number of working hours/tasks.

Mental Fatigue Score: Level of mental exhaustion (0.0 to 10.0).

Target Variable: Burn Rate (0.0 to 1.0).

# Workflow and Technical Pipeline

## 1. Data Cleaning and Imputation

Identified missing values in Resource Allocation, Mental Fatigue Score, and Burn Rate.

Handled non-standard missing values (e.g., ' ', '?', '-').

Imputation Strategy: Utilized SimpleImputer with a mean strategy for numerical variables to maintain data distribution.

## 2. Feature Engineering

Temporal Features: Converted joining dates to datetime objects and extracted the hour of joining for distribution analysis.

Categorical Encoding: Applied One-Hot Encoding to Gender, Company Type, and WFH Setup Available to transform text into a machine-readable format.

Normalization: Applied MinMaxScaler to Resource Allocation and Designation to ensure features are on a consistent scale (0 to 1).

## 3. Exploratory Data Analysis (EDA)

Analyzed gender distributions using bar plots.

<img width="713" height="547" alt="image" src="https://github.com/user-attachments/assets/f0c677c0-9212-4ece-a66e-f82dae168512" />

Examined time-based joining patterns via histograms.

<img width="1023" height="470" alt="image" src="https://github.com/user-attachments/assets/5dad4faa-3ede-4909-ac45-318d81b11bd5" />

Utilized boxplots to check for outliers in joining hours across genders.

<img width="1021" height="547" alt="image" src="https://github.com/user-attachments/assets/c0403bed-2925-4fb6-b79a-ea6e435ef338" />

# Model Development & Evaluation

Three regression models were evaluated to find the best fit for the data:

Linear Regression (Baseline)

Random Forest Regressor (Ensemble)

Gradient Boosting Regressor (Sequential Improvement)

Performance Metrics (Train & Test Results)

Both the training and testing phases yielded highly consistent results:

Model, MAE, MSE, R² Score

Gradient Boosting, 0.0528, 0.0051, 0.8602

Random Forest, 0.0563, 0.0059, 0.8387

Linear Regression, 0.0570, 0.0061, 0.8335

# Key Findings

Top Performer: Gradient Boosting is the most effective algorithm, explaining 86.02% of the variance in burnout rates.

Accuracy: The Mean Absolute Error (MAE) of 0.0528 indicates that predictions deviate by only ~5.3% from actual values.

Non-Linearity: The superior performance of Gradient Boosting suggests that burnout is influenced by complex, non-linear interactions (e.g., how high mental fatigue scales exponentially when combined with poor resource allocation).

Reliability: The consistency between training and testing scores proves the model is not overfitted and is ready for real-world application.

# References
Susan E. J and Randall S. S. (1983). The measurement of experienced burnout. Journal of Occupational Behaviour.
