### Introduction
Emergency Rooms (ERs) are critical components of healthcare systems, yet often suffer from long wait times due to unpredictable demand and limited resources. Predicting these wait times using data-driven approaches can significantly improve hospital efficiency and patient experience.

This project explores the application of machine learning, particularly linear regression, to predict ER wait times based on a subset of features available in a dataset of 5,000 hospital records. The analysis involves feature encoding, model training, and performance evaluation, with a strong emphasis on understanding the relationship between input variables and the predicted wait time.
 
###Objective
The main goal of this project is to develop a predictive model that can estimate ER wait times using historical data. This involves:
Preprocessing and transforming raw features into usable formats
Training a Linear Regression model
Evaluating the model’s predictive performance
Analyzing limitations and proposing future improvements

### Dataset Overview
The dataset contains 5,000 records, each representing a hospital visit with 19 associated features. These include time-based, patient-specific, and hospital-specific variables.

### Selected Features:
For simplicity and interpretability, only three features were selected:

Time of Day: When the patient arrived (e.g., morning, afternoon, night)

Day of Week: Day of the week (e.g., Monday, Tuesday)

Specialist Availability: Count of available specialists at the time

The target variable is:

Total Wait Time: The duration (in minutes) a patient waited before being attended to

### Methodology
1. Data Preprocessing
The dataset was loaded and examined for missing values.

Categorical features (Time of Day, Day of Week) were encoded using Label Encoding to convert them into numerical form.

The dataset was split into training (80%) and testing (20%) subsets.

2. Model Selection
A Linear Regression model was chosen for its simplicity and ability to explain how each input feature contributes to the predicted output.

Linear regression assumes a linear relationship between features and target. While this assumption may not fully hold in real-world hospital data, it serves as a useful baseline.

3. Model Training
The model was trained on the selected features using scikit-learn.

The learned coefficients represent the weights of each feature in predicting wait time.

### Evaluation and Results
The model's performance was assessed using the following metrics:

Metric	Description	Value
MAE	Mean Absolute Error – average prediction error	54.75
MSE	Mean Squared Error – penalizes large errors	4652.10
RMSE	Root Mean Squared Error – interpretable in minutes	68.20
R² Score	Coefficient of Determination – model fit	~0.00

### Interpretation:
The low R² score suggests the model explains almost none of the variability in wait times.

This is expected given the limited feature set and the inherent complexity of ER operations, which are influenced by many unpredictable and non-linear factors.

### Analysis
Why Did the Model Perform Poorly?
Feature Limitation: Only 3 out of 19 features were used.

Encoding Type: Label Encoding imposes an artificial order on categorical data.

Model Choice: Linear regression assumes linearity, which likely doesn't hold in this real-world scenario.

Missing Contextual Variables: Factors such as patient condition, staff workload, hospital crowding, and emergency severity were not included.

### Future Work
To improve performance and applicability, the following steps are recommended:

Feature Expansion:
Incorporate additional variables like patient condition, triage level, historical wait patterns, etc.

Improved Encoding:
Replace Label Encoding with One-Hot Encoding to better represent categorical data without implying order.

Advanced Models:
Use non-linear models such as:
Random Forest Regressor

XGBoost
Neural Networks
Hyperparameter Tuning:
Use GridSearch or RandomizedSearch to find optimal model settings.

Time-Series Approach:

If data is timestamped, implement a time-series model to capture temporal trends.

### Conclusion
This project served as a foundational exploration into ER wait time prediction using a basic machine learning approach. Although the results were not accurate enough for practical deployment, the process illuminated key challenges in healthcare data modeling and pointed toward more advanced solutions.

By integrating richer features and more sophisticated algorithms, predictive models could eventually support hospital staff in decision-making, resource allocation, and improving patient outcomes.


