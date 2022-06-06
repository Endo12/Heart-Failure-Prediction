# Heart-Failure-Prediction
A walkthrough over how I used a machine learning workflow to create an AI model capable of predicting heart failure. Specifically, I have used a linear SVM to categorize data entries as having patients that will either live or die based on their preexisting conditions. Additionally, Pandas is used to store the data, numpy is used to feed the data into our model, and Seaborn is used to visualize model fit. You can view the dataset [here](https://www.kaggle.com/datasets/andrewmvd/heart-failure-clinical-data?resource=download). This project was created for the final submission of BigTh!nk AI, Spring 2022. The steps used are as follows:

## Data Collection
Here, the data is loaded in from CSV files into Pandas datasets. Specifically, we get two datasets: a training set, and much smaller testing set.

## Feature Engineering
This section contains some preanalysis conducted to determine what exactly we should be doing with our data. This includes seeking potential correlations, plotting the dependent variable to determine if class imbalances exist, and making scatterplots of seemingly poor predictor variables to determine if they can be removed.

## Model Selection
This is where the model is created and trained. First, independent variables found to be poor predictors of Death are removed from the dataset. Next, the training set itself is split into its own training/testing set, based on a 80/20 split. Additionally, we found there to be a class imbalance, with most data entries correlating to no death. As such, SMOTE is used to oversample the data entries corresponding to death to have a more balanced training set. It is only now, that our model is created and trained. Here, I use a linear SVM model. The linear SVM model comes from the scikit-learn package; specifically, it uses a sigmoid kernel and balanced class weights to achieve the most accurate model. Finally, the model is used to attempt to predict our data.

## Model Testing
Finally, I tested my model on the testing set and ensured it worked on the training set as well. I did this by plotting basic statistics about the model, like accuracy and CM Score. 
