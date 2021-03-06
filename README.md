
# Neural Network Charity Analysis
Beks has come a long way since her first day at that boot camp five years ago—and since earlier this week, when she started learning about neural networks! Now, she is finally ready to put her skills to work to help the foundation predict where to make investments.

With our knowledge of machine learning and neural networks, we'll use the features in the provided dataset to help Beks create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup. Our goal is to build a deep neural network that will yield accurate predicitions of success by ingesting the dataset.


## Results: Using bulleted lists and images to support your answers, address the following questions.

### Data Preprocessing

### Target Variable
After reviewing the dataset, we consider IS_SUCCESSFUL as the target variable of the neural network. The overall goal of the machine learning process is to determine whether or not the charity donation was used effectively. Our belief is that the binary data in this variable indicate success.


### Model Features
We consider the following variables as features in our neural network model:

- APPLICATION_TYPE
- AFFILIATION
- CLASSIFICATION
- USE_CASE
- ORGANIZATION
- STATUS
- INCOME_AMT
- SPECIAL_CONSIDERATIONS
- ASK_AMT

### Irrelevant variable(s)

We consider the following variables irrelevant to our model and have removed them:

- NAME
- EIN

## Compiling, Training, and Evaluating the Model

### Neural Network Model

We built this deep neural network with the following inputs:

- Two hidden layers, the first containing 88 neurons and second with 55 neurons
- Input dataset with 40 features and 34,299 samples
- Hidden layer Activation function: relu for classification
- Output later Activation fuction: sigmoid in order to normalize results between 0 and 1, ideal for binary classification

### Were we able to achieve the target model performance?

According to our accuracy output below, we were not able to achieve the 80% target accuracy in our neural network model. 

```
268/268 - 1s - loss: 0.5881 - accuracy: 0.7054 - 504ms/epoch - 2ms/step
Loss: 0.5880504250526428, Accuracy: 0.7054227590560913
```

### What steps did we take to try and increase model performance?

In order to improve accuracy, we took the following measures to modify the model:

- Dropped the following additional columns: ORGANIZATION
- Decreased the value cutoff for the application_type_counts bins from 10000 -> 500
- Decreased the value cutoff for the classification_counts bins from 5000 -> 1000
- Doubled the amount of neurons in each hidden layer
- Added a third hidden layer
- Decreased the number of epochs to 50
- Changed the activation to tanh as an alternative form of classifcation

We were able to improve the accuracy of the neural network model, unfortunately still not enouh to hit our 80% target:

```
268/268 - 0s - loss: 0.5656 - accuracy: 0.7221 - 462ms/epoch - 2ms/step
Loss: 0.565593421459198, Accuracy: 0.7220991253852844
```

### Summary

The Neural Network we designed did not deliver the desired accuracy outcome of 80%. Our first iteration delivered 70% accuracy, and second iteration bumped up slightly to 72% accuracy. Given that our target metric contains binary data, we would suggest a supervised Random Forest Classifier model. This alternative model utilizes multiple decision trees to generate a classified output we can evaluate against our existing neural network results.
