# Salary Prediction with Multiple Linear Regression
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A machine learning demonstration project built with Python and Scikit-Learn to predict employee salaries based on multiple independent variables (experience, education level, and English language proficiency), accompanied by data visualization evaluating actual versus predicted outcomes.
## 🚀 Features
- 📊 Trains a Multiple Linear Regression model using scikit-learn to predict continuous target values from multiple features.
- 📈 Extracts and outputs model coefficients and the intercept.
- 📉 Performs salary predictions for new candidate profiles.
- 📊 Generates a scatter plot and a perfect prediction line using matplotlib to visually compare actual versus predicted salaries.

## 🛠️ Tech Stack
- Language: Python 3.x   
- Libraries:pandas (For dataset management and structuring)   
- scikit-learn (For building the linear regression model)   
- matplotlib (For plotting and visual evaluation)   
 
## ⚙️ Getting Started

Make sure you have Python installed, then install the required libraries via pip:
pip install pandas scikit-learn matplotlib

## Installation and running
- Copy the code into your local Jupyter Notebook, Google Colab, or save it as a Python script.
- Execute the script to train the model and generate the evaluation graph:
python multiple_regression.py

📖 Usage
Here is the core code snippet used to train the model and make a prediction for a new data point:

import pandas as pd
from sklearn.linear_model import LinearRegression

# Sample data: experience (years), education (1=Bachelor, 2=Master, 3=PhD), english (0-10), salary
data = {
    "experience": [1, 3, 5, 7, 9, 2, 4, 6],
    "education":  [1, 1, 2, 2, 3, 1, 2, 3],
    "english":    [3, 5, 6, 7, 8, 4, 6, 9],
    "salary":     [18000, 22000, 30000, 35000, 50000, 20000, 32000, 55000]
}

df = pd.DataFrame(data)

# Separate independent variables (X) and target variable (y)
X = df[["experience", "education", "english"]]
y = df["salary"]

# Fit the Multiple Regression model
model = LinearRegression()
model.fit(X, y)

# Predict salary for a new person (e.g., 5 years experience, Master's degree [2], English skill = 7)
new_person = [[5, 2, 7]]
predicted_salary = model.predict(new_person)
print("Predicted Salary:", predicted_salary[0])
