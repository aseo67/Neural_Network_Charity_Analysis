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
  - The feature variables are: **APPLICATION_TYPE**, **AFFILIATION**, **CLASSIFICATION**, **USE_CASE**, **ORGANIZATION**, **STATUS**, **INCOME_AMT**, **SPECIAL_CONSIDERATIONS**, and **ASK_AMT**. These are features that likely play a part in determining the outcome of the model and thus have been included as feature variables. 
- _What variable(s) are neither targets nor features, and should be removed from the input data?_
  - The variables of **EIN** and **NAME** have been removed, as they are neither targets nor features. These two columns are simply identification for each row of data/each application (basically, identification for each and every data point); thus, they do not play a role in determining the outcome of a successful funding or not. 

### Compiling, Training, and Evaluating the Model

- _How many neurons, layers, and activation functions did you select for your neural network model, and why?_
  - To start, 2 layers were used in the neural network model, with 80 neurons in the first layer and 30 in the second layer, given that the number of input features equals ~43, and typically the number of neurons is ~2-3x the amount of input features in a basic network. This model, however, has 2 hidden layers, as this allows some neurons to train on activated input values instead of new training data. 
  - "relu" activation functions were used in the hidden layers. A "sigmoid" function was used in the output layer, given this a classification problem. Since we're looking for a binary yes or no (on whether the funding was successful), this sigmoid function would provide the necessary probability output to help classify this outcome.  
![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Model_build.png)
- _Were you able to achieve the target model performance of 75% accuracy?_
  - No, the level of accuracy achieved with this model was **72.9%**, just below the target of 75%. 
![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Model_evaluate.png)
- _What steps did you take to try and increase model performance?_
  - To try to push the accuracy a bit higher, past 75%, the preprocessing of data was updated first. Two additional columns ("SPECIAL_CONSIDERATIONS" and "STATUS") were removed, as they were hypothesized to not have much of an impact on the success of a funding. "SPECIAL_CONSIDERATIONS" denoted whether there were any special notes to consider about the application (yes or no), and "STATUS" indicated the active status. Furthermore, the binning of the "APPLICATION_TYPE" and "CLASSIFICATION" columns were adjusted a bit to allow a couple more "bins" for the model to consider. 
  ![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V1_dropcols.png)
  ![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V1_apptypebins.png)
  ![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V1_classbins.png)
  ![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V1_finaldf.png)
    - This resulted in an accuracy measure of **~73.0%** when the same model parameters (# of layers, neurons, activation functions, epochs, etc.) were maintained. A slight (but likely negligible) increase vs. the original version of the model, and still under 75%. 
    ![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V1_evaluate.png)
  - Next, an additional layer was added on, and additional neurons included in each layer, to try to improve the accuracy. The first layer now contains 100 neurons, the second contains 50 neurons, and the new third layer contains 20. Each hidden layer still utilizes the "relu" activation function. 
  ![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V2_build.png)
    - This resulted in an accuracy of **~72.8%**, a slight (again, likely negligible) decrease vs. the prior iteration, which means the model stays pretty consistent in accuracy as before. 
    ![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V2_evaluate.png)
  - Finally, a third change was implemented - updating the activation function of the output layer, from a "sigmoid" function to a "tanh" function. The "tanh" function is still suitable for classification problems, so this tests out if a different activation function for the output can help refine the accuracy a bit more. 
  ![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V3_build.png)
    - This resulted in an accuracy of **~72.9%**, again very similar to previous model iterations. 
    ![Screenshot](https://github.com/aseo67/Neural_Network_Charity_Analysis/blob/main/Screenshots/Screenshot_Optimize_V3_evaluate.png)


## Summary
Overall, the model - and the subsequent iterations - all resulted in an accuracy of about 73%, just below the target accuracy of 75%. The initial model was already very close to the target, but subsequent attempts to further refine it were not very successful. 

A potential alternative model that may help solve this classification model is a SVM (Support Vector Machine) model. This type of unsupervised learning model may be more ideal than a deep learning neural network model, as the problem at hand is a simple binary classification (is the funding successful - yes or no). Currently, the deep learning model we have show signs of overfitting as it achieves an accuracy ~73% after just ~20-30 epochs. Multiple tweaks have been made to the model to try and improve the accuracy and help the model to better define the classifier, but not much improvement has been seen. SVMs are less prone to overfitting, as they try to maximize the distance between closest data points of the two groups, rather than try to encompass all the data. This may be a model type that can outperform the deep learning model we have explored in this analysis. 
