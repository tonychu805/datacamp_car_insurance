# Datacamp - Car Insurance Claim

Insurance companies invest a lot of time and money into optimizing their pricing and accurately estimating the likelihood that customers will make a claim. In many countries insurance it is a legal requirement to have car insurance in order to drive a vehicle on public roads, so the market is very large!

Knowing all of this, On the Road car insurance have requested your services in building a model to predict whether a customer will make a claim on their insurance during the policy period. As they have very little expertise and infrastructure for deploying and monitoring machine learning models, they've asked you to identify the single feature that results in the best performing model, as measured by accuracy, so they can start with a simple model in production.

They have supplied you with their customer data as a csv file called car_insurance.csv, along with a table detailing the column names and descriptions below.

## Data

| Column | Description |
|--------|-------------|
| `id` | Unique client identifier |
| `age` | Client's age: <br> <ul><li>`0`: 16-25</li><li>`1`: 26-39</li><li>`2`: 40-64</li><li>`3`: 65+</li></ul> |
| `gender` | Client's gender: <br> <ul><li>`0`: Female</li><li>`1`: Male</li></ul> |
| `driving_experience` | Years the client has been driving: <br> <ul><li>`0`: 0-9</li><li>`1`: 10-19</li><li>`2`: 20-29</li><li>`3`: 30+</li></ul> |
| `education` | Client's level of education: <br> <ul><li>`0`: No education</li><li>`1`: High school</li><li>`2`: University</li></ul> |
| `income` | Client's income level: <br> <ul><li>`0`: Poverty</li><li>`1`: Working class</li><li>`2`: Middle class</li><li>`3`: Upper class</li></ul> |
| `credit_score` | Client's credit score (between zero and one) |
| `vehicle_ownership` | Client's vehicle ownership status: <br><ul><li>`0`: Does not own their vehilce (paying off finance)</li><li>`1`: Owns their vehicle</li></ul> |
| `vehcile_year` | Year of vehicle registration: <br><ul><li>`0`: Before 2015</li><li>`1`: 2015 or later</li></ul> |
| `married` | Client's marital status: <br><ul><li>`0`: Not married</li><li>`1`: Married</li></ul> |
| `children` | Client's number of children |
| `postal_code` | Client's postal code | 
| `annual_mileage` | Number of miles driven by the client each year |
| `vehicle_type` | Type of car: <br> <ul><li>`0`: Sedan</li><li>`1`: Sports car</li></ul> |
| `speeding_violations` | Total number of speeding violations received by the client | 
| `duis` | Number of times the client has been caught driving under the influence of alcohol |
| `past_accidents` | Total number of previous accidents the client has been involved in |
| `outcome` | Whether the client made a claim on their car insurance (response variable): <br><ul><li>`0`: No claim</li><li>`1`: Made a claim</li></ul> |

## Method

### 0. Overview

- To build a model to predict whether a customer will make a claim on car insurance using Logistic Regression

### 1. Exploratory Data Analysis

- Data Cleaning
- Missing Value Imputation
- Standardization
- Check individual features' impact on the outcome and model accuracy

### 2. Model Training

- Remove features that are statistically insignificant
- Perform standardization again
- Split data into training and testing sets
- Train models with all featuers
- Evaluate model performance using accuracy

## Technology

- Pandas, Numpy, Scikit-learn, Seaborn, Scipy

## Results

In terms of overall performance, the relationships between the features and the outcome are intuitive, with the exception of past accidents, which show a negative correlation with claims—a relationship that remains counterintuitive and warrants further investigation. Notably, the model clearly indicates that more experienced drivers are less likely to make claims, and it strongly associates older vehicles with a higher likelihood of claims.

To further enhance the model, following procedures should be performed:
- Model Validation: Perform cross-validation to ensure these results are consistent across different data subsets.
- Further Investigation: Look into the negative correlation between past accidents and claims, as this remains counterintuitive.
- Feature Engineering: Consider creating interaction terms, especially between driving experience and other risk factors.
- Threshold Tuning: While performance is more balanced, you might still want to fine-tune the classification threshold based on the relative costs of false positives vs. false negatives.
- Model Deployment: Given the significant improvement, this model could be considered for deployment after thorough validation and any necessary regulatory approvals.
- Monitoring: Implement a system to monitor the model's performance over time to ensure it maintains its predictive power in real-world applications.

This model provides a strong foundation for predicting insurance claims, offering robust performance across both classes and aligning more closely with intuitive feature relationships.