# multiclassification-text-sentiment

### Summary
This text mining project is an adaption of multiple methods discussed in the text mining lectures. The aim of the project is to classify sentences into one of 8 emotional categories e.g. Anger, Fear, Joy etc. It is a simple implementation, with applications of several text classification methods and particularly the following: 

* Data cleaning methods
* Count vectorisation
* Doc2Vec
* Word2Vec

Due to the size of the database, I have scoped this project such that it is able to train the dataset with predefined word embedding models rather than having to rely on using TensorFlow or keras in the implementation. In this document I will discuss how I implemented the different class codes, what are the methods used and the workflow as mentioned in the above list. Finally I will discuss the results of the experiment.

### Experimental result
Comparing the accuracy and f1 scores of the 20 models I tried, the Count Vectorizing with Support Vector Classification and linear kernel was the best performing model. Taking 1000 random samples in each emotion, I had the result in Fig 1. The top performing model did not change.

The Confusion Matrix in Fig 2 for SVC using balanced data, shows that this model predicts the emotions of the sentences quite well, with Disgust least well predicted. In every case except Anger, using the balanced data was a better predictor than using unbalanced data.

<img width="270" alt="Screenshot 2022-06-02 at 11 32 16" src="https://user-images.githubusercontent.com/1595062/171611333-d2c8701d-f808-4611-aa07-ba8ab4967b51.png">
*Fig 1: Results tables balance training sets*
<br/><br/>

<picture>
<img width="607" alt="Screenshot 2022-06-02 at 11 26 33" src="https://user-images.githubusercontent.com/1595062/171611425-bf45a1d5-6c47-4434-af28-434c45b2787c.png">
*Fig 2: Confusion matrix of CountVec + SVC in a balanced training set*
</picture>
  
### Conclusions
There are several ways to do this in the field of text analytics, however, due to the size of the dataset I focussed on word embedding and decided not to use TensorFlow, keras or other Deep Learning methods used in text classification. 

Balancing the dataset did not allow any model to perform significantly better, in terms of f1 or accuracy scores, than when using the unbalanced dataset, nor to change the fact that SVC with linear kernel was the best performing model. However, when looking at the Confusion Matrix, the SVC model with balanced data performed better than the unbalanced data in predicting the emotion of each sentence, with the only exception being Anger. 
