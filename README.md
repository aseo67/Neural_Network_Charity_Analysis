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
  - asdf
- _Were you able to achieve the target model performance of 75% accuracy?_
  - No, the highest level of accuracy achieved was **73%**. 
- _What steps did you take to try and increase model performance?_
  - asdf


## Summary
Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.
