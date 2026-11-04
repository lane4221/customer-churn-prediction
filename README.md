# Customer Churn Prediction

## Project Description
This project predicts which customers of a telecom company are likely to leave (churn) using a logistic regression model. It uses the Telco Customer Churn dataset from Kaggle, which has 7,043 customers and 21 features covering demographics, services, and account info. The goal is to help the company find at-risk customers early so they can try to keep them.

## Files
- LastName_FirstName_IN503_Unit10_Assignment.ipynb – the full notebook with data exploration, preprocessing, model training, and evaluation
- customer_churn_model.pkl – the saved trained model pipeline

## Installation
1. Clone the repository:
   git clone https://github.com/YOUR-USERNAME/customer-churn-prediction.git
2. Install the required packages:
   pip install pandas numpy matplotlib seaborn scikit-learn joblib kagglehub
3. Open the notebook in Google Colab or Jupyter Notebook and run all cells.

## Usage
Load the saved model and predict churn for a new customer:

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
- Contract type: Month-to-month customers churn the most. Longer contracts keep people around.
- Internet service: Fiber optic customers churn more than DSL or no-internet customers.
- Tenure: New customers are the most likely to leave. The longer someone stays, the less likely they are to churn.
- Pricing: Higher monthly charges are linked to more churn.
- Model performance: Accuracy of __%, with __ precision and __ recall for churned customers.

## Dependencies
- Python 3
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- joblib
- kagglehub
