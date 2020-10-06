# Regression Project - Flight Prediction Project

## Problem Defination
This project is to examine a set of job postings with salaries and then predict salaries for a new set of job postings. Our job is as a data scientist is to create a model which predict the salaries for the job posting.

## Discover the Data

The features in the dataframe are:

+ **Airline**
+ **Date_of_Journey**
+ **Source** 
+ **Destination** 
+ **Route** 
+ **Arrival_Time**
+ **Duration**
+ **Total_Stops**
+ **Additional_Info**
+ **Price**

## Exploratory Data Analysis 

### Basic observations

+ There are total 10 features in the dataset out of which one features are numerical and nine are categorical
+ Total number of observation in the dataset is 10683.
+ Price is our target variable
+ There are no duplicates in the data and there are no values missing in the dataset

### Uni-variate Analysis

![Number of Airlines](https://github.com/DhruTewa/Flight-Price-Prediction-Project/blob/main/Images/1-AIrlines.png)

![Source Cities](https://github.com/DhruTewa/Flight-Price-Prediction-Project/blob/main/Images/2-Source.png)

![Destination Cities](https://github.com/DhruTewa/Flight-Price-Prediction-Project/blob/main/Images/3-Destination.png)

![Number of Stops](https://github.com/DhruTewa/Flight-Price-Prediction-Project/blob/main/Images/4-Stops.png)

### Bi-vairate Analysis

![Airlines vs Price](https://github.com/DhruTewa/Flight-Price-Prediction-Project/blob/main/Images/6-Airline%20vs%20Price.png)


![Source vs Price](https://github.com/DhruTewa/Flight-Price-Prediction-Project/blob/main/Images/7-Source%20vs%20Price.png)


![Destination vs Price](https://github.com/DhruTewa/Flight-Price-Prediction-Project/blob/main/Images/8-Destination%20vs%20Price.png)

## Feature Engineering

+ Created three new feautres from the date features for better model developement
  - Arrival_Hrs
  - Arrival_Mins
  - Departure_Hrs
  - Departrue_mins
  
### Features correlation

![Features_Correlation](https://github.com/DhruTewa/Flight-Price-Prediction-Project/blob/main/Images/9-Correlation.png)


## Data Preprocessing

The datapreprocessing involves steps
 - Onehot Encoding
 - Data Imputation


## Model Developement([code](https://github.com/DhruTewa/Flight-Price-Prediction-Project/blob/main/app.py))

We will evaluate algorithms using the Root Mean Squared Error (RMSE) metric. RMSE will give a gross idea of how wrong all predictions are.We will use 10-fold cross-validation.

- Linear Regression(LR)
- Decision Tree Regressor(DTR)
- Random Forest Regressor(RFR)

The algorithms all use default tuning parameters. By comparing the below table RMSE for Linear regression is the lowest and hence we will select it as the baseline model.

|Model |MSE Value|
|------|---------|
|LR    |-2887.10 |
|DTR   |-2512.91 |
|RFR   |-1986.91 |

![Model Comparision](https://github.com/DhruTewa/Flight-Price-Prediction-Project/blob/main/Images/10-Model%20Comparision.png)

Created a baseline model using Random Forest Regression wit R-square value as **.7837**

### Hyperparameter Tuning

To improve the performance of algorithms, ensemble methods is used. I have used two ensemble machine learning algorithms:

- **Boosting Method** : Gradient Boosting (GBM).
- **Bagging Method**  : Random Forests (RF)

and found Random Search more effective and model building with R-Square **.8050** 

### Feature Importance:

By looking at the graph below we can say that *yearofexperience* and *milesfrommetropolitan* are two major factors in predicting the salary.

![Feature Importance](https://github.com/DhruTewa/Flight-Price-Prediction-Project/blob/main/Images/11-Feature%20Importance.png)

### Model Deployment

Used Flask to deploy the model created:

![Model Deployment](https://github.com/DhruTewa/Flight-Price-Prediction-Project/blob/main/Images/12-Model%20Deployment.PNG)
