# Neural Network Charity Analysis

## Overview
The purpose of this analysis is to create a neural network model that will accurately predict whether or not Alphabet Soup should grant funding for a given project.

## Results
* Data Preprocessing
    - What variable(s) are considered the target(s) for your model?
    The IS_SUCCESSFUL variable is the target.

    - What variable(s) are considered to be the features for your model?
    The features include APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, INCOME_AMT, and ASK_AMT.

    - What variable(s) are neither targets nor features, and should be removed from the input data?
    Out of the 34K+ of data, only 5 rows had a 0 for STATUS. STATUS should not be a feature because it has no weight. SPECIAL_CONSIDERATIONS is just that, a subjective measure that also does not carry weight. STATUS and SPECIAL_CONSIDERATIONS should be removed from the features.

* Compiling, Training, and Evaluating the Model
    - How many neurons, layers, and activation functions did you select for your neural network model, and why?
    Initially we added two hidden layers. The first hidden layer had 80 neurons since we had just over 40 features, keeping in mind the general rule of 2-3 times the amount of features. The first layer we used the RelU activation. The second layer had 40 neurons, half the amount of the first layer, and we used the ReLU activation for it.

    - Were you able to achieve the target model performance?
    With our optimizations we were able to match the performance of the original model, but not outperform it.

    - What steps did you take to try and increase model performance?
    We dropped STATUS and SPECIAL_CONSIDERATIONS from the features, we added 100 neurons to layer 1 and changed its activation to Tanh, we added 50 neurons to layer 2 and changed its activation to Tanh, we added a third layer with 25 neurons and the Tanh activation, and we changed the output activation to ReLU. All of this only matched the original performance.

    Original Neural Network Model
    ![Original Neural Network Model](https://github.com/mjkleineck/Neural_Network_Charity_Analysis/blob/main/Resources/Original.png)

    First Optimization - Removing STATUS and SPECIAL_CONSIDERATIONS from the features
    ![Optimization One](https://github.com/mjkleineck/Neural_Network_Charity_Analysis/blob/main/Resources/Optimization1.png)

    Second Optimization - Dropping STATUS and SPECIAL_CONSIDERATIONS, and adding neurons and an additional hidden layer to see if it make an impact on the accuracy.
    ![Optimization Two](https://github.com/mjkleineck/Neural_Network_Charity_Analysis/blob/main/Resources/Optimization2.png)

    Third Optimization - Dropping STATUS and SPECIAL_CONSIDERATIONS, adding neurons and an additional hidden layer, changing the hidden layer activation to Tanh, and changing the output activation to Relu to see if it make an impact on the accuracy.
    ![Optimization Three](https://github.com/mjkleineck/Neural_Network_Charity_Analysis/blob/main/Resources/Optimization3.png)

## Summary
Overall, machine learning models will help Alphabet Soup determine whether or not to fund various projects. Given the results of trying to leverage a neural network is not the route we would recommend. There are supervised learning models that my provide better accuracy, like Random Forest. A random forest model with a sufficient number of estimators and tree depth should be able to perform at a similar capacity to most deep learning models.
