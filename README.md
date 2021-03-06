# Text-Analytics---LSTM-Network
Objective 

For this project, our objective is to use different deep learning methods to predict the ratings from Yelp reviews solely based on the reviews text. 

LSTM 

LSTM stands for “Long Short-Term Memory.” It is a method used for many regression and time series prediction, but it can be used for text data as well. Utilizing neural networks, LSTM is a variant of Recurrent Neural Networks (RNNS) but have several advantages over them. They solve the problem of exploding and vanishing gradients that often occur with RNNs. This makes them ideal for working with text data. For our project, we sought to categorize reviews into separate review rating categories with LSTMs.  

First Experiment 

As an experiment, we began our modeling with a relatively less complex neural network. On one hand, we set up three limitations in the first experiment. First, we limited the size of the overall vocabulary at 50,000 most-commonly-used words, meaning that we were only utilizing the most frequent words in the training dataset and skipped the ones that are less frequently used. Second, the size of training data was also limited and only 25,000 out of more than 2 million reviews were used. Finally, we also constrained the number count of words for each review and the cap was 200 words for very review.  

On the other hand, we used sigmoid as our activation function for the final dense layer and “binary_crossentropy” as the loss function, and the below table is the actual setting of our LSTM network layers. In the embedding layer, we had the vocabulary size of 50,000 words, output dimensionality of 100 and input length of 200 for each training data point. In the LSTM layer, we had the output dimensionality of 100 and output dimensionality of 6 in the final dense layer. The main reason why the output dimensionality in the final dense layer is 6 is because we have 5 different labels (rating from 1 to 5) and we converted this target variable to a one-hot encoding matrix.  

As a result, the below graph shows a very promising result. After training for only 3 epochs, we were gradually reducing the loss and increasing the predictive accuracy for both training dataset and validation dataset. This experiment was a huge success as we considered all those limitations in this initial experiment. As we observed a simple LSTM network performed well on the small dataset, we decided to train our model on bigger dataset and the accuracies were 90%, 89%, and 68% for training dataset, validation dataset and test dataset respectively. The below graph was the confusion matrix for the test dataset.

Second Experiment 

Upon gaining initial success using a relatively simple LSTM network, we decided to construct a more complex model to see if the predictive accuracy could be improved. On one hand, we increased the size of the overall vocabulary to 80,000 and the size of training data to 1 million reviews, and finally the number count of words for each review was also increased to 300 words for very review.  

On the other hand, the activation function for the final dense layer and the loss function were not changed, and the below table is the actual setting of our LSTM network layers. Overall, the total number of parameters (nodes) in the LSTM network was increased by approximately 3 million and we also trained for 10 epochs as compared with previous setting, and we hope this change could improve the predictive power. However, the accuracy for training dataset was gradually increasing from 88% to 92% while validation dataset’s accuracy was consistently around 89% and no any indication for major improvement was observed. In addition, similar outcome was found in the test dataset and the accuracy was also 68%. As shown in the below confusion matrix for the test dataset, there were no obvious changes, except that the number of predictions for rating 3 was slightly increased as the number of predictions for other categories decreased such as rating 1 and 2.
