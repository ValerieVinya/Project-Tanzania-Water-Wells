# Phase III Project: Using classification model to predict the functionality of Tanzania water wells.

## Overview
Tanzania is a developing country that struggles to get clean water to its population of 63.59 million people as of 2021.

The goal of this project is to construct a classification model that can be used to predict the condition of water wells in Tanzania. This model will classify the condition of water wells into 3 categories namely:-

- functional - the waterpoint is operational and there are no repairs needed
- functional needs repair - the waterpoint is operational but needs repairs
- non-functional - the waterpoint is not operational

To construct this model, we used the data from Taarifa and the Tanzanian Ministry of Water. The approach for this project is to follow the OSEMN framework. The steps of this framework are as follows:-

- Obtain the data
- Scrub the data
- Explore the data
- Model the data
- Interpret the data

### Obtaining the Data
The data from Taarifa and the Tanzanian Ministry of Water is originally divided into 3 CSV files -

  - Test set values: The independent variables that need predictions

  - Training set labels: The dependent variable (status_group) for each of the rows in Training set values

  - Training set values: The independent variables for the training set

Since there are no labels for the test dataset, we primarily use the training dataset to construct the model as well as test the various scores of the model. Then use the values of test data to generate predictions.

## Business and Data Understanding

### Stakeholder
- Our project is focused on addressing a critical issue in Tanzania, a developing country where access to clean water is a major challenge for its population of over 63 million. 

- The primary goal is to develop a classification model capable of predicting the condition of water wells across the country. This model is not only for government bodies and NGOs working in Tanzania but also for local communities and international aid organizations seeking to allocate resources effectively.

## Modeling
- We had 39 estimators to predict the conditions of the wells.

- We developed 5 different classifiers:-
  - Support Vector Machines
  - K-Nearest Neighbour
  - Decision Tree
  - XGBoost
  - Random forest

  ![download](https://github.com/nguro23/Project-Tanzania-Water-Wells/assets/142256019/7251768b-b682-4e87-a95d-dc63a073eb54)

- Our metrics of success were based on Accuracy and F1 scores:-

<img width="339" alt="image" src="https://github.com/nguro23/Project-Tanzania-Water-Wells/assets/142256019/1c4832ba-c27c-4c2a-ab90-c97e7ee6d824">


## Evaluation

- As per the plot, some of the model performances are fairly close but the Random Forest Classifier with GridSearchCV has the overall highest scores.

- The Accuracy and F1 scores around 70% are not great but it is significantly better than 33% of randomly selecting between 3 labels.

<img width="430" alt="image" src="https://github.com/nguro23/Project-Tanzania-Water-Wells/assets/142256019/87f2b8c3-81b6-4db7-86ae-42233ed1c872">


<img width="473" alt="image" src="https://github.com/nguro23/Project-Tanzania-Water-Wells/assets/142256019/1bf9114f-a073-4243-a991-43ca226e139e">


## Recommendations and Conclusions
- The Random Forest Classifier with GridSearchCV has recall scores of 0.5 for functional needs repair and 0.71 for non-functional. There are some models such as XGBoost and Support Vector machines which have higher recall scores for functional needs repair labels but the Random Forest Classifier with GridSearchCV model has the highest recall score for non-functional. Therefore, we will select the Random Tree Classifier with GridSearchCV as our model since it has the highest accuracy, f1, and recall score for non-functional labels.

- The areas that we need to work on further to improve the final model are as below:-

    - The range of hyperparameter input that I use in GridSearchCV for various models is quite limited due to the computing power of my desktop. For example, we couldn't       successfully use GridSearchCV for Support vector machines because it took a very long time to complete. The model performance will be better if a larger range of input is   used to find the optimal hyperparameters.

    - We removed multiple features before the model constructions because we believed these features were irrelevant. Some of these features might be relevant and could help in improving my model's performance metrics.

    - As part of the data scrubbing, we used a min-max scaler to normalize our datasets. Possibly, our model's performance metrics might improve if we use other methods such as standardization instead of a min-max scaler.







