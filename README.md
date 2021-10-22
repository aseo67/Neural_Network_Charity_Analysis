# Neural Network Charity Analysis
Module 19 Challenge Files
- [AlphabetSoupCharity.ipynb](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/AlphabetSoupCharity.ipynb)
- [AlphabetSoupCharity.h5](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/AlphabetSoupCharity.h5)
- [AlphabetSoupCharity_Optimization.ipynb](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/AlphabetSoupCharity_Optimization.ipynb)
- [AlphabetSoupCharity_Optimization.h5](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/AlphabetSoupCharity_Optimization.h5)
- [checkpoints](https://github.com/aseo67/Neural_Network_Charity_Analysis/tree/main/checkpoints)
- [checkpoints_optimization](https://github.com/aseo67/Neural_Network_Charity_Analysis/tree/main/checkpoints_optimization)
- [Resources](https://github.com/aseo67/Neural_Network_Charity_Analysis/tree/main/Resources)
- [Screenshots](https://github.com/aseo67/Neural_Network_Charity_Analysis/tree/main/Screenshots)


## Overview of Analysis
A nonprofit called Alphabet Soup is looking to create a binary classifier that can predict whether applicants will be successful if they receive funding from the organization. A dataset of more than 34,000 organizations who have received funding from Alphabet Soup is used to build the model. This dataset contains information on: identification for each applicant, application type, affiliated sector of industry, government organization classification, use case for funding, organization type, active status, income classification, special considerations, funding amount requested, and whether money was used effectively. Using these variables, the following analysis explores a deep learning model that can help determine whether applicants will be successful with Alphabet Soup's funding. 


## Results

### Data Preprocessing

- _What variable(s) are considered the target(s) for your model?_
  - The target variable for this model is the **IS_SUCCESSFUL** variable, as this outlines the result/outcome of whether an application/organization who received funding was successful or not. 
- _What variable(s) are considered to be the features for your model?_
  - The feature variables are: **APPLICATION_TYPE**, **AFFILIATION**, **CLASSIFICATION**, **USE_CASE**, **ORGANIZATION**, **STATUS**, **INCOME_AMT**, **SPECIAL_CONSIDERATIONS**, and **ASK_AMT**. These are features that play role in determining the outcome of the model. 
- _What variable(s) are neither targets nor features, and should be removed from the input data?_
  - The variables of **EIN** and **NAME** have been removed, as they are neither targets nor features. These two columns are simply identification for each row of data/each application (basically, identification for each and every data point); thus, they do not play a role in determining the outcome of a successful funding or not. 

### Compiling, Training, and Evaluating the Model

- _How many neurons, layers, and activation functions did you select for your neural network model, and why?_
  - To start, 2 layers were used in the neural network model, with 80 neurons in the first layer and 30 in the second layer, given that the number of input features equals ~43, and typically the number of neurons is ~2-3x the amount of input features in a basic network. This model, however, has 2 hidden layers, as this allows some neurons to train on activated input values instead of new training data. Thus, the model can better identify nonlinear characteristics of input data. 
  - "relu" activation functions were used in the hidden layers. A "sigmoid" function was used in the output layer, given this a classification problem. Since we're looking for a binary yes or no (on whether the funding was successful), this sigmoid function would provide the necessary probability output to help classify this outcome.  
![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Model_build.png)
- _Were you able to achieve the target model performance of 75% accuracy?_
  - No, the level of accuracy achieved with this model was **72.9%**. 
[Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Model_evaluate.png)
- _What steps did you take to try and increase model performance?_
  - asdf
![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V1_dropcols.png)
![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V1_apptypebins.png)
![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V1_classbins.png)
![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V1_finaldf.png)
![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V1_evaluate.png)
  - Then
![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V2_build.png)
![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V2_evaluate.png)
  - Finally, 
![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V3_build.png)
![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V3_evaluate.png)


## Summary
Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.
