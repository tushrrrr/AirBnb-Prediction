# AirBnb Prediction

## DATASET AND FEATURES

Dataset is from Kaggle which had New york’s Airbnb listings and other geographical metrics to make predictions. 
The whole dataset had about 153254 rows and 106 columns. We have ‘Price’ as our target variable. 
As we are dealing with a target variable of numerical data we will use a regression method to predict the values. 

## EXPLORATORY DATA ANALYSIS 

Packages Used : 

NUMPY: To perform mathematical operations on the dataset 

PANDAS: Used for data analysis and cleaning 

MATPLOTLIB: Used to plot the graphs

PANDAS-PROFILING: Used to better understand the features of the dataset and their statistics 

## DATA PRE-PROCESSING 

The first step was cleaning the data like dropping unnecessary columns, filling in the null values, and so on. 
The first thing in the Preprocessing step was to count the number of null values for each column. 
If an attribute had more than 60 percent of null values, then we assumed that this column does not have enough information and is meaningless, so we dropped these columns. 
We checked for missing values in our dataset. In case there were any missing entries, we imputed them with appropriate values (mode in case of categorical feature, and median or mean in case of numerical feature).

<img width="395" alt="image" src="https://user-images.githubusercontent.com/114719570/204112730-b07388e1-5909-49c3-a02a-7c0f1850955e.png">

The graphical representation of the percentage of missing values in each column. 

After finding the missing values, the columns that had missing values more than 60% of the dataset were removed as they did not contribute to the model. And then by looking through the details of each attribute, we can further drop more columns. 

We started with Univariate Analysis to find the distribution of each column. We used a bar graph for this purpose. The missing values for categorical columns have been replaced with the most occurring ones by visualizing the value_counts of the column. The majority of the categories fall under ‘Within an hour’ by looking at the bar plot. Hence the missing values are replaced with ‘Within an hour’ using the fillna() method. 

<img width="337" alt="image" src="https://user-images.githubusercontent.com/114719570/204112740-4b41a9b2-f334-4576-83a8-8a3a9f5f6c5c.png">

The graphical representation of the percentage of missing values in each column. 

## OUTLIERS DETECTION 

Boxplots are a standardized way of displaying the distribution of data based on a five-number summary (“minimum”, first quartile (Q1), median, third quartile (Q3), and “maximum”). This type of plot is used to easily detect outliers. It can also tell us if your data is symmetrical, how tightly your data is grouped, and if and how your data is skewed. 

<img width="386" alt="image" src="https://user-images.githubusercontent.com/114719570/204112751-69e31e42-7c26-4789-b926-14b95097be11.png">

## Principal Component Analysis (PCA) 

Performed PCA with 0.9 for the number of component parameters. Scikit Learn chooses the minimum number of principal components such that 90% of the variance is retained. By doing this, the number of features was reduced from 106 to 48. 

<img width="468" alt="image" src="https://user-images.githubusercontent.com/114719570/204112767-836f1ef0-15fb-4662-8efe-eebb6b355341.png">

## MODEL EVALUATION 

LinearRegression 
LogisticRegression 
Ridge Regression 
Lasso Regression
Elastic net
GradientBoosting Regressor 
SVR (Support Vector Regression) 
RandomForestRegressor 

<img width="326" alt="image" src="https://user-images.githubusercontent.com/114719570/204112786-9e3eff47-e8f9-4dd3-a78d-51278f0e31ad.png">

<img width="387" alt="image" src="https://user-images.githubusercontent.com/114719570/204112791-09c023c6-e1b5-4302-b4ed-f740ca95fa72.png">

## CONCLUSION 

In conclusion, we compared diff erent models based on the Root Mean Square Error(RMSE) and Median Absolute Error(MAE) evaluation metric. Linear models are simple; however, it was not quite adequate for prediction on this dataset. Ensemble learning has uncertain performance based on the choice of models. Therefore, in the real-life problem, we cannot depend on only one of a few speci fic models, we need to compare di erent models using some high-level techniques. As the main model that we used is SVR, first run was done with the plain model and then used the GridSearchCV to find the best hyperparameters to tune the SVR. MAE(Median Absolute Error) is used as a loss function to compare the models being used because it predicts the error as the diff erence between the predicted and actual which yields a numeric value that can be easily correlated. 
