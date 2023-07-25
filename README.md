## Background 

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. 


## Overview of the analysis

The purpose of the analysis is to build a binary classifier using machine learning and neural networks to predict whether applicants will be successful, if they are funded by the nonprofit foundation Alphabet Soup. The goal is to develop a tool that can assist the business team in selecting the applicants with the best chance of success in their ventures, based on the provided dataset. <br></br>
The dataset contains information on more than 34,000 organizations that have previously received funding from Alphabet Soup. The dataset includes various columns capturing metadata about each organization. These metadata features are likely attributes or characteristics of the organizations that may have some correlation with their success or failure.

## Results
### Data Preprocessing
  
  - Target Variable(s): The target variable for the model is the `"IS_SUCCESSFUL"` column, which indicates whether the funding was used effectively (1) or not (0).

  - Features Variable(s): The features for the model include the following columns:

`APPLICATION_TYPE`: Alphabet Soup application type; <br>
`AFFILIATION`: Affiliated sector of industry; <br>
`CLASSIFICATION`: Government organization classification; <br>
`USE_CASE`: Use case for funding; <br>
`ORGANIZATION`: Organization type; <br>
`INCOME_AMT`: Income classification; <br>
`ASK_AMT`: Funding amount requested. <br>

<br>

- Variables that should be removed from the input data because they are neither targets nor features:

`"EIN"` and  `"NAME"` columns were removed for the 1st and 2nd attempts, as they were not directly linked to the probability of success. 
`"SPECIAL_CONSIDERATIONS"` column, additionally was removed for the 3rd attempt, it did not improve accuracy of the model. 

<br>

### Compiling, Training, and Evaluating the Model

  - Model Structure

**First attempt**: the neural network model utilizes 2 hidden layers, because an ideal starting point for NNM’s is 2-4 layers. There are 43 features so 86 neurons, or 2-3 times the amount of input features were used for the first hidden node. The second hidden node used 43 neurons and 100 training epochs respectively. 
The reLU activation function was utilized, because it is ideal for modeling positive, nonlinear input data for classification or regression. The sigmoid function was utilized, because its values are normalized to a probability between 0 and 1, which is ideal for a binary classification dataset.

**Second attempt**: the neural network model utilizes 3 hidden layers with 129, 86 and 43 neurons with 150 training epochs. The reLU activation and sigmoid functions were utilized. 

**Third attempt**: the neural network model utilizes 4 hidden layers with 172, 129, 86 and 43 neurons with 200 training epochs. The reLU activation and sigmoid functions were utilized as well.

<br>

 - Model Accuracy


The first model had an accuracy score of 72.49%. After increasing the number of neurons and layers, the second model had an accuracy score of 72.59%. After increasing the epochs, the third model had an accuracy score of 72.47%. These models did not reach the target model performance of 75%.


<br>

- Steps to Increase Model Performance


To increase model performance, the model’s neurons, layers and epochs were changed. In the second attempt at modeling, the 3rd hidden reLU layer was added, the model has still not met performance expectations, that's why we increase the number of training epochs from 100 to 150. As the number of epochs increases, so does the amount of information provided to each neuron, adding more epochs also increases likelihood that model will achieve optimal weight coefficient.

In the third attempt to increase model performance, the model’s neurons, layers and epochs were changed as well. The 4th hidden reLU layer was added and the epochs were increased from 150 to 200. Neurons changed from 129, 86, 43 to 172, 129, 86 and 43 neurons. Adding more neurons speeds up the model and may reduce loss. Adding more layers considers more interactions between variables.

<br>

## Summary: 
 
 - Model Overview <br>
This deep learning model aimed to predict if a company would be classified as successful or no successful based on features of their application. Out of the three models, the highest accuracy score was 72.59% with the loss of 59.2%. These results are not accurate enough for the clients threshold of 75% so more modeling attempts with different hyperparameters would need to be built to create a more reliable binary classifier.


 - Additional Model Recommendation <br>
Another model that could solve this classification problem is the Perceptron or linear binary classifier. The perceptron model mimics a biological neuron by receiving input data, weighting the information, and producing a clear output. It would be a good alternative method for classification, because the model separates and classifies the data into two groups using linear equation. For the purpose of this project, those two groups would be successful and not successful.

