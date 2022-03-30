# Neural Network Charity Analysis

## Overview

### Purpose
Beks is a data scientist and programmer for the non-profit foundation Alphabet Soup.  This organization prides themselves in trying to protect the environment, improve wellbeing, and unify the world.  They have raised and donated over $10 Billion in the last 20 years.  Beks is in charge of data collection and analysis and her job is to analyze the impact of each donation and vet potential recipients to make sure the donations are being well used.  The president of Alphabet Soup has reached out to Beks to predict which organizations are worth donating to and which are too high risks.

## Analysis and Results

### Analysis
Beks will design and train a deep learning neural network using the TensorFlow library.  The reliability of the model will be evaluated to see if it can accurately predict optimal donation candidates from a variety of input variables.  

### Results

#### Data Preprocessing
The dataset has 34,299 different investments.

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
    * I also considered dropping Status from the dataset as an optimization since only 5 of the 34,299 data points have a status of 0 and all other data points have a status of 1.  This did not impact model performance and was not saved as one of the 3 optimization cases.   

#### Compiling, Training, and Evaluating the Model
* How many neurons, layers, and activation functions did you select for your neural network model, and why?
    * Initially neurons and layers were chosen to match the output shape and parameters from the sample code provided (i.e. 80 in the first layer and 30 in the second layer)
    * Lower numbers were ran as well (i.e. 10 in the first layer and 3 in the second layer) to see if complexity and time could be reduced while accuracy could be maintained.  73.3% accuracy was obtained with 10 and 3 while 73.9% was obtained with 80 and 30.  This different is not significant and either could be considered for ongoing modeling.  80 and 30 was kept to match the started code deliverable.   

<p align="center">
  <img src = https://github.com/lauras521/Neural_Network_Charity_Analysis/blob/58186eb2005c61e03377e6cf423c251e0661f2cc/Resources/ModelSummaryD1D2.PNG>
</p>

* Were you able to achieve the target model performance?
    * Target model performance above 75% was not obtained.  The best model plateaued below 75%.
     
* What steps did you take to try and increase model performance?
    * The following 3 optimizations were ran: 
    
     1. Outliers were removed from the ASK_AMT data column.  After reviewing this dataset, there are quite a few outliers on the high side that skew the data.  The thought was the model might be giving this column more weight than necessary.  The IQR ranges from 887 - 11,855.  Of the 34,299 donation requests 25,398 of them asked for 5,000.  8,901 other requests asked for more than 5,000.  The 18 largest requests asked totaled 50,671,612,115 and made up 53% of the entire column's sum for all 34,299 requests.  The firm invested $10 billion over the last 20 years and the top 18 requests total over 50 billion.  As a result, it doesn't appear the data is in dollars or there is an error in some of the data.  The removal of the noisy outlier data did not play out as anticipated in model accuracy.  This model ran with a lower accuracy of 55.2%.   
     2. The second attempt added back in the outliers from ASK_AMT and added a 3rd hidden layer, increased epochs from 50 to 100 and changed the model from relu to tanh.  This model ran to 74.2% accuracy.
     3. The third attempt added additional neurons to hidden layers 1 and 2 and a 3rd hidden layer was added.  This model ran to 74.1% accuracy. 

As a result, no attempts were able to increase model accuracy above 75%.

### Summary

This deep learning model accurately predicts successful donations ~75% of the time.  Other supervised learning classification models (i.e. logistic regression) could be used for this analysis as you have the necessary input data and desired results.  This model was attempted and had similar accuracy performance but could take less time, space, and code to run so could be worth exploring further.     


## Resources
[link to Deliverable 1 and 2 code](https://github.com/lauras521/Neural_Network_Charity_Analysis/blob/27e2b58cbfd1b4f75da65297b26a0ac8bbb52564/AlphabetSoupCharity.ipynb)

[link to Deliverable 3 Optimization 1](https://github.com/lauras521/Neural_Network_Charity_Analysis/blob/27e2b58cbfd1b4f75da65297b26a0ac8bbb52564/AlphabetSoupCharity_Optimization1.ipynb)

[link to Deliverable 3 Optimization 2](https://github.com/lauras521/Neural_Network_Charity_Analysis/blob/27e2b58cbfd1b4f75da65297b26a0ac8bbb52564/AlphabetSoupCharity_Optimization2.ipynb)

[link to Deliverable 3 Optimization 3](https://github.com/lauras521/Neural_Network_Charity_Analysis/blob/27e2b58cbfd1b4f75da65297b26a0ac8bbb52564/AlphabetSoupCharity_Optimization3.ipynb)
