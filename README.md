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
## Training 
The data was was trained by turning weak learning algorithms into strong learners. The data went through a set of decision trees and each decision tree pushed aside easier weights to train on classifying difficult weights.
## Accuracy Score 
![](https://github.com/jonathansylvestre/GroupProject/blob/51f6e59f1fce26394034b372477a0e3ab60f1ca0/Resources/Screen%20Shot%202022-01-20%20at%208.23.32%20PM.png)

The GradBoost model was able to calculate the highest accuracy score of 79.

## Database

  Once we identified the best model for the data selected, we moved on to the next step which was to integrate a database to store both the cleaned data and our results. After reviewing the results of the model, we then combined our results with the cleaned data in order to have all the data in one table or dataframe. When dealing with the data storage part of the project, we selected PostgreSQL which is a free and open-source relational database management system emphasizing extensibility and SQL compliance. As we had previous experience with PostgreSQL via pgAdmin 4, it was only right that we use this tool in order to complete this task. We started by creating an entity relationship diagram (ERD) to provide us with a visual starting point for database design that could also be used to help determine information system requirements. Once that was complete we created the database (Job Changes) where we would save our tables. Once the database was created, we built our first table using a downloaded cleaned data CSV file from our jupiter notebook file. Before importing the CSV, we had to created the table and columns required to correctly import the information on the CSV. Using the import wizard we were able load the data from the CSV to the  previously created table and respective columns. 

## Dashboard

Once our tables are saved in our database, we are able to move on to our next step which is which is to create a dashboard using our predictions. For this of our project, we will be selecting Tableau Software to create our visualizations for our results. We will create multiple visuals which will be combined in order to create our dashboard as seen below. 

![](https://github.com/jonathansylvestre/GroupProject/blob/main/Resources/Who%20is%20in%20the%20job%20market.png)

In order to create these displays, we will be downloading our "Results" table from our database to a CSV in order to upload it to Tableau. Once we have successfully uploaded the table into tableau, we can begin creating our visualizations on each sheet. 

 - Using the "Prediction" columns, we are able to visualize in a pie chart, the number of positive results vs the amount of negative results from our prediction.
 - Using the "City" and the "Prediction" columns, we will be able to display in a horizontal bar chart, the top 10 cities with the highest amount of positive results from our model. 
 - Using the "City" and the "City Development Index" columns, we are able to display in a line chart, the city develompment index of the previously mentioned top 10 cities.
 - Using the "Gender" and the "Prediction" columns, we are able visualize the distribution of positive results on a gender basis in a bar chart.
 - Using the "Prediction" and the "Company Size" columns, we will create a pie chart which displays the amount of positive results based on the company size. 
 - Using the "Prediction" and the "Company Type" columns, we will create a table which displays the amount of positive results based on the company type.
 - Using the "Prediction" and the "Education Level" columns, we are able to use a bubble chart in order to display the distribution of positive results based on the candidate's education level. 
 - Using the "Prediction" and the "Major Discipline" columns, we are able to use treemaps to visualize which major has the strongest amount of positive predictions.

Once all of our visualizations are created individually in Tableau, they can be combined in a dashboard so they can all be seen on the same page. This will enable us to identify the features to look for or not to look for in a potential candidate. 

## Conclusion
In conclusion we can found out that the features with the most insight on which candidates to avoid when considering applicants are the specific city, the development index of it, company size, and gender. City 103 must be a major city because the majority of turnover can be predicted to originate from there. Although the industry is dominated by men, they are 10 times more likely to look for another job than females. Company size also plays a big role as applicants from the 50-99 range appear to be on the move compared to those at much larger companies. If these models were to be improved, it should be suggested to only test and train these 4 features to see how it would affect the accuracy score.