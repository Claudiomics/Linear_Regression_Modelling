# Linear/Non-Linear Regression_Modelling

## Introduction

This is a project which will help me build a solid understanding of fitting data to linear and non-linear regression models in python, while showcasing my familiarity with statistical tests and visualisation techniques. This is my first data project using biological test data, and it is one of my life goals to be able to develop novel therapeutics through the use of compute power and AI, so here I am working towards my goals. My previous project with Peregrine inlcuded credit card data to a logistic regression model, which classifies the variables into binary classes, and I would like to expand on this knowledge with linear and non-linear regression models.

During my time with Peregrine, I was pushed into the deep end with the ML projects, so am going back to the basics to fully understand the stats and maths behind these ML so I can make better descisions when working with novel data sets.

My aim is to take a biological assay data set, fit it to a model and interpret the results, using tools like scikit-learn and Matplotlib. This data set from SUPPORT2 is made up of 9105 rows and 47 columns, and with it I will use a logitic regression model to predict if the patient will live 2 months or 6 months, so the doctor can provide a data-based prognosis. The large number of observations means the model is quite complex.

## So what is Regression Modelling?

Regression Modelling is a kind of statistical analysis which allows the user to predict the future outcome of something based on the data available. The model is built to analyse the relationship between the independant variable(s) and the depenant variable. For example, in a clinical drug dose-response relationship, the independent variable (input) would be the dose of the drug, whereas the dependentant variable (output) would be the response to the drug.

### Linear Regression 

Linear regression is a model used to quantify causal relationships in a data set. The outcome will be continous, for example predicting the price of a house based on it's size.

The mathematical expression is:

```
y = bx
```

where

```
y - dependant variable (house price)
b - coefficient (represents the distribution of observations)
x - independant variable (house size)
```

This is plotted as a straight line on a graph, with x on the horizontal axis and y on the veritcal axis.

### Logistic Regression

Logistic regression is a linear model used for binary classification, such as determining whether an email is spam or not-spam. Although logistic regression itself is linear, it uses a non-linear activation function, the sigmoid, to map predicted values to probabilities between 0 and 1. Based on a threshold (commonly 0.5), these probabilities can be converted into binary outcomes (1 or 0). The sigmoid function gives logistic regression its characteristic "S-shaped" curve.

In logistic regression, the linear combination of the predictors is calculated, and then transformed using the logistic function to map it to a probability.

The mathematical expression for the linear part of the model - the linear combination of the predictors (sometimes referred to as the logit or log-odds):

```
y = a + b1x1 + b2x2 ... bnxn
```

where 

```
y   dependant variable
a   y-intercept (value of y if x=0)
b   coefficient for each independent variable (change in the log-odds of y for a one-unit increase in x)
x   independent variables
```
This is the weighted sum of the predictors. This linear combination produces a continuous value that could range from negative to positive infinity.

This is then inputted into the sigmoid function to convert it to a probability (non-linear transformation):

```
P(y=1)  =   1 / (1 + e ^ -z)
```
where
```
P(y=1)  probability that the outcome is in target class 1
z       linear combination
```
The sigmoid squashes any real-valued input into a range between 0 and 1, which can be interpreted as a probability.

The overall expression is:
```
P(y=1)  =   1   /   (1 + e ^ -(a + b1x1 + b2x2 ... + bnxn))
```
To summarise, the linear combination (z) represents the log-odds of y being 1 (the odds of the positive class occurring).
Applying the sigmoid function to the log-odds maps this output to a probability between 0 and 1.

#### Cluster Analysis

This is where certain observations are grouped together. For example if a group of houses is small and expensive, they are likely city houses. Big and inexpensive could be far from the city but not in nice neighbourhoods. Big and expensive could be far from the city in nice neighbourhoods.

These clustes can be seen clearly when plotted on a graph.

#### Factor Analysis

If the independant variables are grouped together due to similarity, this is called factor analysis, and is used to simplify the model and increases accuracy.

So if x1, x2 and x3 all were a score of how much someone liked animals, if they were an animal lover and if they are against animal cruelty, then Z1 would be the factor of the general attitude to animals.

```
x1, x2, x3 --> Z1
```

The expression would become:

```
z = n + n1z1 + n2z2 n3z3
```


### Non-Linear Regession

Some examples of non-linear regression include polynomial regression, exponential regression, logarhythmic regression, power regression and logistic growth model. 

I will focus on these later on in my personal growth journey.

## Methods: CRISP-DM

I am following the Cross-Industry Standard Process for Data Mining framework to ensure my workflow is logical and efficient.

### 1. Business Understanding

### 2. Data Understanding

#### 2.1 Finding and Loading in the Data

I will use the [SUPPORT2](https://archive.ics.uci.edu/dataset/880/support2) data set from the UCI ML repo, which holds 9105 rows of data from critically ill patients across 5 US medical centers, accessioned throughout 1989-1991 and 1992-1994. The patients are divided into 9 disease categories including acute respiratory failure, chronic obstructive pulmonary disease, congestive heart failure, liver disease, coma, colon cancer, lung cancer, multiple organ system failure with malignancy, and multiple organ system failure with sepsis.

My project aims to predict length of patient stay, which will influence descision making in relation to disease prognosis.

I loaded in the data using code provided by the UCI ML repo: 

`pip install ucimlrepo` # import the ucimlrepo package

#then download the dataset
`from ucimlrepo import fetch_ucirepo`
  
#fetch dataset 
`support2 = fetch_ucirepo(id=880)` 
  
#data (as pandas dataframes) 
`X = support2.data.features` 
`y = support2.data.targets` 
  
#metadata 
`print(support2.metadata)` 
  
#variable information 
`print(support2.variables)`

The official dataset information reccommends some input to fill in missing values, as no preprocessing has occured, which will be completed in the following steps.

#### 2.2 Checking 

## Conclusion
