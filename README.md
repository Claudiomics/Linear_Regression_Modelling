# Linear/Non-Linear Regression_Modelling

## Introduction

This is a project which will help me build a solid understanding of fitting data to linear and non-linear regression models in python, while showcasing my familiarity with statistical tests and visualisation techniques. This is my first data project using biological test data, and it is one of my life goals to be able to develop novel therapeutics through the use of compute power and AI, so here I am working towards my goals. My previous project with Peregrine inlcuded credit card data to a logistic regression model, which classifies the variables into binary classes, and I would like to expand on this knowledge with linear and non-linear regression models.

My aim is to take a biological assay data set, fit it to a model and interpret the results, using tools like scikit-learn and Matplotlib.

## So what is Regression Modelling?

Regression Modelling is a kind of statistical analysis which allows the user to predict the future outcome of something based on the data available. The model is built to analyse the relationship between the independant variable(s) and the depenant variable. For example, in a clinical drug dose-response relationship, the independent variable (input) would be the dose of the drug, whereas the dependentant variable (output) would be the response to the drug.

### Linear and Non-Linear Regression 

Where the outcome will be continuous, for example predicting a person's weight based on their height.

### Logistic Regression

Where the outcome is divided into categories, for example if mail is classified as spam or not-spam (binary classifcation).

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
