# neural-network-challenge-2
AI camp module 19 challenge

# Overview

You are tasked with creating a neural network that HR can use to predict whether employees are likely to leave the company. Additionally, HR believes that some employees may be better suited to other departments, so you are also asked to predict the department that best fits each employee. These two columns should be predicted using a branched neural network.

# Part 1: Preprocessing 
Import the data and view the first five rows. Determine the number of unique values in each column. Create y_df with the attrition and department columns. Create a list of at least 10 column names to use as X data. You can choose any 10 columns you’d like EXCEPT the attrition and department columns. Create X_df using your selected columns. Show the data types for X_df. Split the data into training and testing sets. Convert your X data to numeric data types however you see fit. Add new code cells as necessary. Make sure to fit any encoders to the training data, and then transform both the training and testing data. Create a StandardScaler, fit the scaler to the training data, and then transform both the training and testing data. Create a OneHotEncoder for the department column, then fit the encoder to the training data and use it to transform both the training and testing data. Create a OneHotEncoder for the attrition column, then fit the encoder to the training data and use it to transform both the training and testing data.

# Create, Compile, and Train the Model
Find the number of columns in the X training data. Create the input layer. Do NOT use a sequential model, as there will be two branched output layers. Create at least two shared layers. Create a branch to predict the department target column. Use one hidden layer and one output layer. Create a branch to predict the attrition target column. Use one hidden layer and one output layer. Create the model. Compile the model. Summarize the model. Train the model using the preprocessed data. Evaluate the model with the testing data. Print the accuracy for both department and attrition.


# Summary
In the provided space below, briefly answer the following questions.

1. Is accuracy the best metric to use on this data? Why or why not?
- Accuracy is a reasonable starting metric for this data but possibly is not the absolute best metric for the complete dataset. Accuracy generally describes how the model performed across all classes when all classes are of equal importance. With this data there is a possibility that we haven't accounted for the imbalance in data and the underlying reasoning. The attrition metric could be misleading in the number of people who have not left compared the number of people who have left that would influence the accuracy of this model. We could look to incorporate different metrics like Precision which reflects how reliable the model is in classifying samples as positive. We could also utilize Recall metric to help establish how many correctly classified positive results were observed with this model. Ultimately a combination of multiple metrics would help provide a better indication of performance rather than a single metric. While there may not be any real cost implications in misidentifying a person as likely to leave vs likely to stay, having stronger metrics would enhance the model and possibly provde more effective. 

2. What activation functions did you choose for your output layers, and why?
- My selection for relu as the activation fuction for shared and hidden layers because it is a reliable function that is helps mitigate the vanishing gradient problem which can occur when training with many neural netowrk models. The Attrition output selection to use sigmoid is based on a binary classification problem and is well suited for limiting the probability between 0 and 1 which is helpful for this problem of a stay or leave binary answer. The Department output select to use softmax as it is a reliable multi-class classification function that is designed to make outputs easier to interpret. 

3. Can you name a few ways that this model might be improved?
- While this model was reasonably useful in the results it provided the list below would help improve the model results with iterative changes and re-testing: 
    - Data collection: gather more supportive data to be included in the data set to help the model learn more
    - Managing data imblance: identification of which data elements in use are not balanced and selecting different data or applying more balance would help improve the model
    - Hyperparameter tuning: experimenting with changes in the number of layers in use, the number of epochs, batch sizes, learning rates, activation functions to find the best performance and scoring
    - Feature engineering: adjusting data elements selected for features to find the most accurate results


# Reference
https://blog.paperspace.com/deep-learning-metrics-precision-recall-accuracy/
