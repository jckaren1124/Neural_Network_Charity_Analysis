# Neural_Network_Charity_Analysis

## Overview of the analysis
Alphabet Soup is a large nonprofit foundation that raises and distributes donations for various nonprofit organizations.  In order to ensure maximum usage of the donated funds, neural network models will be utilized to determine which recipients are considered high risk and which organizations are most effective at producing results.

## Results
### **Data Preprocessing**
* The target variable in the dataset is "IS_SUCCESSFUL" as the goal of the model is to predict which organizations are successful in using the allocated funds and which are not.
* The feature variables in the data set would include "APPLICATION TYPE", "AFFILIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "STATUS", "INCOME_AMT", "SPECIAL_CONSIDERATIONS", and "ASK_AMT".

![image](https://user-images.githubusercontent.com/89353378/152621414-5d20ce66-ace1-47a4-893f-8ae127731f3c.png)

* "EIN" and "NAME" columns would not contribute any meaningful value to whether a nonprofit organization is successful, so these two variables were dropped in the dataset when generating the neural network model.


### **Compiling, Training, and Evaluating the Model**
* Since the dataset is quite large and complex with 9 different feature variables, the neural network model was originally set with 80 neurons in the first hidden layer, 30 neurons in the second hidden layer, and 3 activation functions (the two hidden layers used the relu activation function while the output layer utilized the sigmoid activation function).
* After training, compiling, and evaluating the model, the accuracy rate was only 54%, which is below the target model performance of 75%.
![image](https://user-images.githubusercontent.com/89353378/152622762-5964067c-1438-40ce-8830-845f652ca087.png)

* Three unsuccessful attempts were made to reach the 75% target model performance as described below:
  * First attempt: Neurons in the first hidden layer were increased from 80 to 120 while the second hidden layer neurons were increased from 30 to 80.  This resulted in only a slightly higher accuracy rate of 57%.
 
   ![image](https://user-images.githubusercontent.com/89353378/152624671-fff34a25-cbc9-4f81-980e-02aace77ab7c.png)

  * Second attempt: Two additional hidden layers with 80 neurons were added (total of 4 hidden layers) to the neural network model from the first attempt, and the accuracy rate was lowered to 51%.

   ![image](https://user-images.githubusercontent.com/89353378/152624704-c52450ba-7086-4a68-8455-9e6ad3ab7348.png)

  * Third attempt: Different types of activation functions were changed for the hidden layers.  However, this also proved to be ineffective as the accuracy rate also remained at 51%.

   ![image](https://user-images.githubusercontent.com/89353378/152624734-c8b1e42f-959a-412d-990a-962dab8f027c.png)




## Summary
In summary, the overall model performance was low even after multiple attempts were made to improve the neural network model.  This low model performance could possibly be due to improper training of the model from a small dataset.  However, since there are 34,299 data points in the dataset, this indicates that the dataset is much more complex than originally anticipated.  Perhaps the data points have too much variance.  If that is the case, we can try using the logistic regression model with random forest classifier.  This model can rank the importance of features when determining relationships.
