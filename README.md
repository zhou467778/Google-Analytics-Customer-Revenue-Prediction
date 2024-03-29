# Google-Analytics-Customer-Revenue-Prediction
## Objective
This study validates the 80/20 rule at Google’s merchandise store by analyzing the revenue concentration from a select group of customers. Utilizing Kaggle’s 2016-2017 dataset, we initially applied preprocessing techniques, including timestamp transformation and natural language processing, to extract vital information. Subsequently, various classification models were employed to forecast customer purchase behavior. The models demonstrated high accuracy: 0.90 for original cleaned data, 0.83 for downsampled, and 0.95 for oversampled data. A time series model was also developed, showing robust predictive capability. These findings underscore the significance of precise marketing strategies to effectively utilize customer data for optimizing revenue.
## Study Design
### Part one: Classification to predict if a customer will make a purchase based on available customer information and web traffic
#### 1. Data Preparation
- Removed 24 constant features from the dataset
- Removed 5 features that contain more than 96% null values
- Added one categorical feature as the target value for the classification problem: value 0 as user did not make any purchase; 1 as user did make purchase
- From analysis, we found that most of users who made purchase were from the United States, so we decided to narrow down our data to only focus on users who are located in the United States for further analysis
- Transfered the provided UNIX timestamp feature to user's local timestamp based on user's location by applying a Python API - GeoPy, and add extra time features, such as hour, weekday and month
- Did Natural Language Processing for 3 text-based features
#### 2. Exploratory Data Analysis
- Visualized the distribution of each categorical feature and continuous variables among all users to observe if transactions were made or not
#### 3. Feature Selection
- Applied the Label Encoder method to encode all catrgorical variables and generated a heatmap of the entire dataset
- Conducted Chi-Squared Test of Indepence for some categorical features
#### 4. Imbalanced Dataset
- Experimented with SMOTE (Synthetic Minority Oversampling Technique) for oversampling and the NearMiss Algorithm for undersampling
#### 5. Methodology
- Logistic Regression
- Random Forest
- XGboost
- Support Vector Machine
- Light GBM
- Multilayer Perceptron
### Part two: Time-series prediction to predict the daily total transaction revenue
#### 1. Data Processing
- Calculate the target variable for prediction - daily total transaction revenue by aggregating the transaction revenue for each customer, grouped by day
#### 2. Model
- ARMA
- SARIMAX
- ARIMAX
