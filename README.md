# GroupProject Outline

## Topic 
The data provided presents insight on whether or not potential job candidates truthfully want to work as Data Scientists for the company or are only going through the hiring process as a way to obtain free training and use it to land positions elsewhere. Human resource researchers are trying to pinpoint certain factors in these candidates to reduce attrition and save on training expenses.

## Abstract
In order to predict the probability of a candidate sticking with the company, exploratory data analysis was done to discover facts about the dataset. A density plot was created on the training hours feature to compare the experience levels of the candidates. It was discovered that the majority of the candidates had less than 50 hours of training in Data Science at the time they began taking courses with the company. The machine learning model that will be used is Random Over Sampling because the dataset has apparant class imbalances. In order to gain indepth insight on the model, multiple datasets will be manipulated and experimented on to discover patterns among features so that HR can make effective decisions in their hiring process. This research will be conducted using a lot of methods such as tools from sklearn, python, and held on PgAdmin. 

## Source of Data
https://www.kaggle.com/arashnic/hr-analytics-job-change-of-data-scientists?select=aug_test.csv

## Goals
In this project we wish to find out what key indicators will enable the HR researchers to make effective hiring decisions when considering applicants who have passed their trainings based on education, experience, and origin city.

## Communication Protocols
Collaboration for this project will be done using Slack & Zoom

## Preliminary Preprocessing 

* The preliminary data preprocessing consisted of cleaning the data to ensure that all data was consistent in format and filling in null-values in each column. 

## Preliminary Feature Engineering 

* Put the data through a RandomForest model to select columns like enrolled university and city to be dropped as features.  Column experience was an object transformed into numeric value as the rest of object typed columns were hot encoded to be categorical features. 

## Split Data
* The data was split by creating variables for the features and target columns. The checked the count in the target columns to see for any imbalances. 

## Model

* The model is an imbalanced dataset. So many of the over sampling type of algorithms were used to see which one was better at classifying people as either looking or not looking for a job. The gradient boosting model had the best precision and recall when it came to classifying people not looking for a job.

* The limitations of this model are that its prone to overfitting, sensitive to outliers, and doesn’t perform well on unsupervised learning data.

* The benefits of this model are its robustness, able to handle datasets with missing data points, works well with categorical and numerical values.  

