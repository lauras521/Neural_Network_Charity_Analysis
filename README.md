# Neural Network Charity Analysis

## Overview

### Purpose
Beks is a data scientist and programmer for the non-profit foundation Alphabet Soup.  This organization prides themselves in trying to protect the environment, improve well being, and unify the world.  They have raised and donated over $10 Billion in the last 20 years.  Beks is in charge of data collection and analysis and her job is to analyze the impact of each donation and vet potential recipients to make sure the donations are being well used.  The president of Alphabet Soup has reached out to Beks to predict which organizations are worth donating to and which are too high risks.

## Analysis and Results

### Analysis
Beks will design and train a deep learning neural network using the TensorFlow library.  The reliabilty of the model will be evaluated to see if it can accurately predict optimal donation candidiates from a variety of input varibles.  

### Results
The dataset has 34299 different investments.

* The target variable for this model is the "IS_SUCCESSFUL" column.  This will be the output column the neural network is trying to predict.
* The features for the model are the following:
    * Application Type
    * Affiliation
    * Classification
    * Use_Case
    * Organization
    * Status 
    * Income Amount
    * Special Consideration
    * Ask Amount
* Name and EIN were dropped from the data set as they didn't add value to the analysis
    * We also considered dropping Status from the dataset as an optimization since only 5 of the 34299 data points have a status of 0 and all other data points have a status of 1.  This did not impact model performance and was not saved as one of the 3 optimization cases.   

#### Compiling, Training, and Evaluating the Model
How many neurons, layers, and activation functions did you select for your neural network model, and why?
Were you able to achieve the target model performance?
What steps did you take to try and increase model performance?


<p align="center">
  <img src = >
</p>

Hvplot_table was used to have a user friendly view of the raw data.

<p align="center">
  <img src = >
</p>

### Summary

Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.



1. dropped status column
2. added 3rd hidden layer
3. increased to 100 epocs and updaed to tanh

## Resources
[link to Deliverable 1 and 2 code](https://github.com/lauras521/Neural_Network_Charity_Analysis/blob/27e2b58cbfd1b4f75da65297b26a0ac8bbb52564/AlphabetSoupCharity.ipynb)

[link to Deliverable 3 Optimization 1](https://github.com/lauras521/Neural_Network_Charity_Analysis/blob/27e2b58cbfd1b4f75da65297b26a0ac8bbb52564/AlphabetSoupCharity_Optimization1.ipynb)

[link to Deliverable 3 Optimization 2](https://github.com/lauras521/Neural_Network_Charity_Analysis/blob/27e2b58cbfd1b4f75da65297b26a0ac8bbb52564/AlphabetSoupCharity_Optimization2.ipynb)

[link to Deliverable 3 Optimization 3](https://github.com/lauras521/Neural_Network_Charity_Analysis/blob/27e2b58cbfd1b4f75da65297b26a0ac8bbb52564/AlphabetSoupCharity_Optimization3.ipynb)
