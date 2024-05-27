# e-Commerce Analysis
Project 4 - Group 3

- Ali Yazdan
- Ashrita Surisetti
- Malini Sintre

### INTRODUCTION
In the rapidly evolving landscape of e-commerce, understanding customer behavior and efficiently categorising products are pivotal for enhancing user experience and optimising inventory management. 
Our project aims to address these challenges through a comprehensive analysis and a robust machine learning model.

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

![alt text](image.png)

### EXPLORATORY DATA ANALYSIS

1. Key Performance Indicators (KPIs)
![alt text](image-2.png)

2. Top Products and Categories

![alt text](image-8.png)

3. Shopper Behaviour

![alt text](image-9.png)

![alt text](image-11.png)

4. Sales Analysis

![alt text](image-10.png)

5. Analysis by hour of the day, day of the week, and day of the month.
Identified peak times for user activity.

![alt text](image-6.png)

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

![alt text](image-12.png)

- Plotted learning_curve to check if this is an overfitting issue as below and the training curve is a straigh line indicating that the model isn't learning well from the training data and training and validation curves are not following the trend. So, the next step is to optimise the model.

![alt text](image-13.png)

**Hyperparameter Tuning**

- Manually adjusted hyperparameters like max_depth, min_samples_split to reduce overfitting and accuracy is 89% with low recall and f1-scores indicating there is stil a room for improvement.

![alt text](image-14.png)
 

- Employed GridSearchCV for automatic hyperparameter optimisation and the final accuracy is 95% with improved recall and f1-scores as shown below.

![alt text](image-15.png)

- Plotted learning curve again to check the model performance.

![alt text](image-16.png)

**Analysis:** From the learning curve, it is evedent that learning and validation curves are following the same trend indicating that the model is performing well on both train and test sets, it is neither overfitting or underfitting.

Also, RandomForestClassifier model is performing well with accuracy and precision at 95%, recall and f1-scores at ~96%.

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

![alt text](image-17.png)

**Model Training and Evaluation**
- Data Preparation for Machine Learning
- Model Training and Evaluation - Trained 3 models as shown below

![alt text](image-19.png)

- Feature Importance Analysis
- Grid Search for Hyperparameter Tuning
- Final Model Training and Evaluation using larger sample

- Overall results of all 3 models

![alt text](image-20.png)


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


