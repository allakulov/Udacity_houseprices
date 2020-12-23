# Udacity Data Scientist Capstone
## Kaggle Competition: House Prices - Advanced Regression Techniques

##  1. Business Understanding:
This project sets out to analyze the Ames Housing datasets, which are provided as part of a Kaggle competition available here: https://www.kaggle.com/c/house-prices-advanced-regression-techniques/overview

The project aims to answer the following main questions:
1. What different segments of houses can we identify in the dataset?
2. Can we predict house prices with high accuracy using the available attributes? 
3. What are the important attributes that influence the final sale prices of houses?


##  2. Data Understanding:
The Ames Housing dataset was compiled by Dean De Cock for use in data science education. The following are the datasets used in this project:

- train.csv - the training set 

- test.csv - the test set

- data_description.txt - full description of each column, originally prepared by Dean De Cock but lightly edited to match the column names used here


## 3. Data Preparation:

To begin with, attributes with high percentage of values missing are identified and removed. Next, the preprocessing of data is done in two main parts: preprocessing of categorical attributes and numerical attributes:

- categorical attributes: first, the categorical attributes are imputed using the most frequent value strategy. Next, dummy variables are created. To do this, categories are identified using a combined dataset of the train and test datasets. 
- numerical attributes: numerical attributes are preprocessed in two steps. In the first step, only continuous features are dealt with. To do this, new features are created using the existing features. After that, the continuous attributes are imputed using KNN imputer, which is fit on the combined dataset of the train and test sets. In the next stage, ordinal attributes are preprocessed. First, the ordinal attributes are imputed using the most frequent value strategy. Next, ordinal encoding is applied to the ordinal attributes. To achieve the desired order values, dictionaries of values are created and fit into OrdinalEncoder. 

The train and test datasets are preprocessed simultaneously to ensure consistency in their structures and features. 

## 4. Modeling:
The project has two main models: unsupervised ML and supervised ML. 
- Unsupervised ML: Principal component analysis (PCA) is applied to the training dataset to reduce the dimensionality. Next, k-means clustering is conducted uing the selected components from the PCA analysis. Using the elbow method, four main clusters are identified and analyzed. 

- Supervised ML: first, the number of features are reduced using recursive feature elimination (RFE).To do this, a Gradient Boosting Regressor model is evaluated with different numbers of features. The number of features that yield the smallest root mean squared error is selected for the next phase. Using the selected features, RandomizedSearchCV is used to tune hyperparameters of the model and to evaluate different models using cross-validation. Finally, feature importances of the selected regression model are evaluated.

## 5. Evaluation:
The final Gradient Boosting Regressor model yields a very small root mean square log error of 0.013933917176273583. 


## 6. Structure of the Project

- data
|- train.csv 
|- test.csv 
|- data_description.txt 

- documentation
|- README.md
|- Udacity_Data_Scientist_Capstone.pdf



**Author
Umrbek Allakulov**