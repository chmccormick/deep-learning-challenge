# deep-learning-challenge
# Alphabet Soup Neural Network Model 

## Overview 
In this analysis I was tasked with building a neural network model for the nonprofit foundation, Alphabet Soup. The goal of the model was to select applicants for funding with the best chance of success. I implemented several tools to build a successful nerual network model on the data provided.

## Data Preprocessing 
### What variable(s) are the target(s) for your model?
The target variable for this model was the 'IS_SUCCESSFUL' column. This column is our binary classification outcome variable that will ultimatley determine if applicants will be success if funded by Alphabet Soup. 

### What variable(s) are the features for your model?
The feature variables of this model were include all other columns of the dataframe except the target column ('IS_SUCCESSFUL'). This includes the following columns: 
- 'APPLICATION_TYPE'
- 'AFFILIATION'
- 'CLASSIFICATION'
- 'USE_CASE'
- 'ORGANIZATION'
- 'STATUS'
- 'INCOME_AMT'
- 'SPECIAL_CONSIDERATIONS'
- 'ASK_AMT'

(During step 3, I attempted to optimize the model by including the 'NAME' column as a feature, which proved to increase accuracy). 

### What variable(s) should be removed from the input data because they are neither targets nor features?
I initially removed both the 'EIN' and 'NAME' columns from the dataframe. During step 3, I only excluded the 'EIN' and keeped the 'NAME' column as a feature as an experiment to see how it would effect the accuracy score of my model. 

## Compiling, Training, and Evaluating the Model 
### How many neurons, layers, and activation functions did you select for your neural network model, and why?
I decided to add 2 hidden layers in addition to my input layer and my ouptput layer. Both of my hidden layers have similar number of neurons (my first hidden layer has 10 neurons and my second hidden layer has 8 neurons). I used the relu activation function for my input layer and my hidden layers as thhe relu activation provided the best results. I used the sigmoid activation in my output layer as I needed the output to be in binary format. 

### Were you able to achieve the target model performance?
Initially, I was only able to achieve an accuracy score of around 72%. I attempted adjusting the number of hidden layers, number of neuors, and activation functions to improve this accuracy score, but the score remained between 72% and 73%. After experimenting with the columns (features), I was able to achieve a much higher accuracy score of 77%. 

### What steps did you take in your attempts to increase model performance?
As mentioned previously, I decdided to keep the 'NAME' column as a feature to imporve model performance. I also decided to adjust the number of hidden layers and neurons. In my optimization attempt, I added 3 hidden layers. While maintaining the same output layer specifications as I did before. Here is a breakdown of each layer: 
hidden layer 1 : 23 neurons, relu activation function
hidden layer 2 : 30 neurons, sigmoid activation function. 
hidden layer 3 : 7 neurons, sigmoid activation function. 

I settled on these adjustments (keeping 'NAME' as feature, adding layers, neurons) as they proved to provide the best accuracy score. I implemented the use of the TensorFlow playground to decide on the number of neurons and layers. 

Outside of these two adjustments, everything else remained identical to my first attempt. 


## Summary 
In summary, the final model that was implemented on the data achieved a predictive accuracy score of 76% - 77%. I used several different methods to optimize this model, including adding/removing feature columns, adding hidden layers and neurons, binning categorical features, and testing the model with different activation functions in each layer. Arriving to an accuracy score of 77% required extensive optimization testing. 

As it was considerably difficult to obtain an accuracy score >= 75%, I would maybe suggest experimenting with different model types, such as the Random Forest Classifier. A Random Forest model might prove to be more successful or as successful as my model with less effort to optimize it. A Random Forest model would also be able to handle both numerical and categorical variables as eaisly as my model did. Another benefit to using a Random Forest model could be that it may shed some light on any outliers or imbalanced data.  

