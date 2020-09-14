# Machine Learning Data PreProcessing Using R Project 1:

•	Data preprocessing is the crucial step in making a ML model.

•	If there is no data preprocessing step on the data, your ML model won't work properly.

|Languages Used: | R|
|---|---|

|IDE Used: | RStudio|
|--- |--- |

Pre-processing steps to do to prepare any dataset on which we will build ML model.

## Get the Dataset:

The first step is always to get the dataset and try to understand dataset. Try to figure out what all are independent variables and what are dependent variables. In ML, some independent variables are used to predict a dependent variable.

The name of the dataset I have taken is 'purchase_data.csv'.

Dataset contains four columns -> Country, Age, Salary, Purchased. Dataset has total 10 observations.

Dataset contains information of customers of some company and first three columns are information of a customer like country, age, salary and fourth column tell if the customer has purchased the product of the company or not.

In purchase_data.csv, first three columns i.e. Country, Age, Salary are independent variables whereas fourth column Purchased is dependent variable.

## Import the Dataset:

## Dealing with Missing Data:

Your dataset may contain missing data. In purchase_data.csv, we can see that there is one missing data in the age column for Spain and one missing data in salary column for Germany.

One way to deal with missing data is to remove the lines of the observation where there is some missing data but that can be dangerous because the data set may contain crucial information. So, it is quite dangerous to remove observation.

Another way to handle missing data is to take the mean of the columns. So, in age column where we have missing entry for Spain, we will replace this missing data by the mean of all the values in the column age.

In R, we can write if else condition to check missing data and take mean of that column if the condition holds true.

## Encode Categorical Data:

Your dataset may contain quantitative and qualitative variables. Quantitative variables contain numeric values whereas qualitative variables contain the categories or levels within the data.

ML models are based on mathematical equations, so it would cause some problem if we keep the text and use categorical variables in the equation because ML Model want only numbers in the equations. That's why we need to encode categorical variables.

In 'purchase_data.csv', Country and Purchased are two categorical variables because they simply contain categories.

•	Country variable contains three categories - France, Spain, Germany

•	Purchased variable contains two categories - yes, no

In R, we use factor function to transform a categorical variable to numeric variable.

## Split the Dataset into Training Data and Test Data:

ML is about a machine that is going to learn from the data to make predictions.

We need to split the dataset into training set and test set. Using training set, we build the machine learning model and using test set, we test the performance of this machine learning model.

We are building our ML model on training set by establishing some correlation between independent variables and dependent variables and once the ML model understands the correlation between independent variables and dependent variables we will test if the ML model can apply the correlations you understood based on training set on test set.

In nutshell, we have to make two different datasets. The training set on which the machine learning model learns and test set on which we test if the ML model learned correctly the correlations.

In R, caTools library is used to split the dataset into training and test set.

## Feature Scaling:

In the dataset, the variables age and salary are not on the same scale because the Age is ranging from 27 to 50 and Salary is ranging 40k to 90k.

We need to have these variables in the same scale otherwise their distance (or Euclidean Distance) would be dominated by the variable with high range.

Standardization and normalization are two ways of doing feature scaling.

In R, we use scale function.
