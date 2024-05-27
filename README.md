# e-Commerce Analysis
Project 4 - Group 3

- Ali Yazdan
- Ashrita Surisetti
- Malini Sintre

### INTRODUCTION
In the rapidly evolving landscape of e-commerce, understanding customer behavior and efficiently categorising products are pivotal for enhancing user experience and optimising inventory management. 
Our project aims to address these challenges through a comprehensive analysis and a robust machine-learning model.

### PROJECT OVERVIEW

- Analyse e-Commerce Customer Behaviour
- Product and Brand Analysis
- Sales Analysis by Product
- Product Category Classification
- Predict the Customer Engagement 

### DATA CLEANING AND TRANSFORMATION

1. Initial Data Check
2. Data Cleaning
3. Feature Engineering
4. Filtering and Mapping
5. Category and Product Mapping
6. Final Feature Engineering
7. Saving Cleaned Data

Overview of data processing:

![image](https://github.com/AshritaSurisetti/project-4-group-3/assets/147963279/18fcc5fb-5496-4a11-9553-a02dcbebd146)


### EXPLORATORY DATA ANALYSIS

1. Key Performance Indicators (KPIs)

![image-2](https://github.com/AshritaSurisetti/project-4-group-3/assets/147963279/d66f58f4-39bc-4b4b-9d96-3bbd84593a30)


2. Top Products and Categories

<img width="314" alt="image-8" src="https://github.com/AshritaSurisetti/project-4-group-3/assets/147963279/b4f98bfc-3c00-45db-b8d3-2f55b67925c9">


3. Shopper Behaviour

<img width="113" alt="image-9" src="https://github.com/AshritaSurisetti/project-4-group-3/assets/147963279/bc70df6a-1a09-4ae4-bd34-94bbb395a9e2">

<img width="238" alt="image-11" src="https://github.com/AshritaSurisetti/project-4-group-3/assets/147963279/c75d73b2-541a-45bf-af3a-2ea17c62b1f4">


4. Sales Analysis

<img width="238" alt="image-11" src="https://github.com/AshritaSurisetti/project-4-group-3/assets/147963279/f4224ae4-de31-439a-813a-a173046ae029">


5. Analysis by hour of the day, day of the week, and day of the month.
Identified peak times for user activity.

![image-6](https://github.com/AshritaSurisetti/project-4-group-3/assets/147963279/f207d2ce-3d63-4169-b990-a592aa4ee905)


## MACHINE LEARNING 

### PRODUCT CATEGORY CLASSIFICATION

**Objective:** To classify the products into categories

**Data Usage:** 

- Initially trained the model using 1 GB of data but did not achieve the expected accuracy.
- To improve runtime and data efficiency, aggregated columns and merged categories with the least counts.
- Final dataset size reduced to 300 MB, consisting of 1.9 million rows

**Data Preprocessing for Machine Learning**

- Resampled 10% of the data with 190,000 records and considered 42 unique Product Categories.
- Balanced the dominant class to avoid bias.

**Feature Engineering for Machine Learning**

- Used “feature_importances_” and removed unnecessary columns
- Encoded Categorical variables using “LabelEncoder”
- Scaled numerical variables using “StandardScaler”

**Model Training and Optimisation**

**Initial Training**
- Split the data into train and test sets using “train_test_split” function.
- Used RandomForestClassifier model and trained it. The classification report is shown in the image below indicating potential overfitting issue.

![image-12](https://github.com/AshritaSurisetti/project-4-group-3/assets/147963279/27ae05b3-2424-4e6e-9dae-e575d2d38eb6)


- Plotted learning_curve to check if this is an overfitting issue as below and the training curve is a straigh line indicating that the model isn't learning well from the training data and training and validation curves are not following the trend. So, the next step is to optimise the model.

![image-13](https://github.com/AshritaSurisetti/project-4-group-3/assets/147963279/4734426f-8b30-452e-95e9-cf0ac918c904)


**Hyperparameter Tuning**

- Manually adjusted hyperparameters like max_depth, min_samples_split to reduce overfitting and accuracy is 89% with low recall and f1-scores indicating there is stil a room for improvement.

![image-14](https://github.com/AshritaSurisetti/project-4-group-3/assets/147963279/10e2b7f8-15ed-4896-81f4-82f4dccc18f8)

 

- Employed GridSearchCV for automatic hyperparameter optimisation and the final accuracy is 95% with improved recall and f1-scores as shown below.

![image-15](https://github.com/AshritaSurisetti/project-4-group-3/assets/147963279/cbdac799-b1be-4004-bfdb-4dd74a9e515e)


- Plotted learning curve again to check the model performance.

![image-16](https://github.com/AshritaSurisetti/project-4-group-3/assets/147963279/16e3c5c9-ae54-424d-a6aa-48ef100ac2e5)

**Analysis:** From the learning curve, it is evident that learning and validation curves are following the same trend indicating that the model is performing well on both train and test sets, it is neither overfitting nor underfitting.

Also, RandomForestClassifier model is performing well with accuracy and precision at 95%, recall, and f1-scores at ~96%.

## MACHINE LEARNING MODEL - 2

### PREDICT CUSTOMER ENGAGEMENT

**Data Preprocessing**
- Creating SQLAlchemy Engine and Loading Data
- Data Type Optimization Category and Price Binning
- Handling Missing Values and Duplicates
- Stratified Sampling
- Principal Component Analysis (PCA)
- Correlation Analysis
- Feature Engineering

**Identifying the important features using Heatmap**

![image-17](https://github.com/AshritaSurisetti/project-4-group-3/assets/147963279/74ea0d54-e8c8-4702-b5fd-6ba19234e096)


**Model Training and Evaluation**
- Data Preparation for Machine Learning
- Model Training and Evaluation - Trained 3 models as shown below

![image-19](https://github.com/AshritaSurisetti/project-4-group-3/assets/147963279/e4b7c73e-c046-48ea-8070-a508f1965ae6)


- Feature Importance Analysis
- Grid Search for Hyperparameter Tuning
- Final Model Training and Evaluation using larger sample

- Overall results of all 3 models

![image-18](https://github.com/AshritaSurisetti/project-4-group-3/assets/147963279/006d33d4-420f-4485-9af6-0ce193599835)

## CONCLUSION 

**Most Efficient Model:**

The very low MSE and high R² indicate that the Random Forest model fits the data extremely well, making very accurate predictions.

**Usability:**
- Visitor Engagement
- Personalization
- Resource Allocation
- Trend Analysis
- Target peak shopping times with promotions.

**Real World Practice:**
- Use the trained models to score new data and predict the total actions for new or existing visitors.

- Segment your visitors based on predicted actions. Identify top, middle, and low engagement segments to tailor your marketing strategies.

**Limitations:**
- Data compression may lead to information loss.
- Data coverage is for the period Nov 2019 - April 2020; trends may vary over time.


### REFERENCES
- Kaggle
https://www.kaggle.com/datasets/mkechinov/ecommerce-behavior-data-from-multi-category-store/data

- ChatGPT
https://chatgpt.com/?oai-dm=1

- StackOverflow
https://stackoverflow.com/


