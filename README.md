# Customer Churn Prediction

## Project Description
This project predicts which customers are likely to leave a telecom company using logistic regression. I used the Telco Customer Churn dataset from Kaggle, which has 7,043 customers.

## Files
- Meadows_Lane_IN503_Unit10_Assignment.ipynb – the notebook with all the code
- customer_churn_model.pkl – the saved model

## Installation
1. Clone the repo:
   git clone https://github.com/YOUR-USERNAME/customer-churn-prediction.git
2. Install the packages:
   pip install pandas numpy matplotlib seaborn scikit-learn joblib kagglehub
3. Open the notebook in Google Colab and run all the cells.

## Usage
Load the model and predict if a new customer will leave:

    import joblib
    import pandas as pd

    model = joblib.load('customer_churn_model.pkl')

    new_customer = pd.DataFrame({
        'gender': ['Male'], 'SeniorCitizen': [0], 'Partner': ['No'], 'Dependents': ['No'],
        'tenure': [1], 'PhoneService': ['Yes'], 'MultipleLines': ['No'],
        'InternetService': ['Fiber optic'], 'OnlineSecurity': ['No'], 'OnlineBackup': ['No'],
        'DeviceProtection': ['No'], 'TechSupport': ['No'], 'StreamingTV': ['No'],
        'StreamingMovies': ['No'], 'Contract': ['Month-to-month'], 'PaperlessBilling': ['Yes'],
        'PaymentMethod': ['Electronic check'], 'MonthlyCharges': [75.75], 'TotalCharges': [75.75]
    })

    prediction = model.predict(new_customer)
    print('Churn' if prediction[0] == 1 else 'No Churn')

## Key Findings
- Month-to-month customers leave the most
- Fiber optic customers leave more than DSL or no-internet customers
- Newer customers are the most likely to leave
- Higher monthly charges go with more churn
- The model got 80.38% accuracy, 0.65 precision, and 0.57 recall for churn

## Dependencies
- Python 3
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- joblib
- kagglehub
