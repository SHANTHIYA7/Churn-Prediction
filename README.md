# Churn-Prediction
I’ll review the notebook’s model workflow and results sections so the GitHub README accurately describes the project, methods, and evaluation instead of using generic churn language.

Read , lines 310 to 635

# Customer Churn Prediction

This project predicts whether a bank-card customer is likely to leave the bank. The analysis uses customer demographics, account information, credit behavior, transaction activity, and inactivity patterns to identify potential churners.

## Business Objective

Customer attrition can reduce revenue and increase the cost of acquiring new customers. By identifying customers at risk of leaving, banks can take proactive retention actions such as personalized offers, improved services, and targeted communication.

The main objective is to predict `Attrition_Flag`:

- `0`: Existing Customer
- `1`: Attrited Customer

## Dataset Features

The dataset includes:

- Customer age and gender
- Education and income category
- Marital status and card category
- Number of dependents
- Customer relationship count
- Months inactive during the last 12 months
- Number of customer-service contacts
- Credit limit and revolving balance
- Average open-to-buy amount
- Transaction amounts and changes
- Average utilization ratio

`CLIENTNUM` is removed because it is only an identification field and does not contribute to churn prediction.

## Data Preprocessing

The project includes:

- Dataset inspection and descriptive analysis
- Removal of the customer identification column
- Conversion of the target into binary values
- Ordinal encoding of education and income categories
- One-hot encoding of marital status, card category, and gender
- Stratified train-test splitting to preserve the churn ratio

The data is divided into:

- 80% training data
- 20% testing data

## Machine Learning Models

Three classification models are compared:

1. Decision Tree
2. Random Forest
3. Gradient Boosting

## Evaluation Metrics

The models are evaluated using:

- Accuracy
- Precision
- Recall
- F1-score

Recall is especially important because failing to identify a likely churner may result in a lost retention opportunity. Precision is also considered to avoid directing retention resources toward customers who are unlikely to leave.

## Final Result

Gradient Boosting performs best on the held-out test data:

- Accuracy: `0.964`
- Precision: `0.957`
- Recall: `0.812`
- F1-score: `0.879`

It provides the strongest balance between identifying churners and minimizing unnecessary retention actions. Before deployment, the model should be validated through cross-validation and monitored regularly for changes in customer behavior and performance.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook
