# Hyperparameter-Optimization-Grid-Search-CV

## Implementation

1. Define the hyperparameters and their possible values
This is the first step for the grid search method; we need to specify the range of values for each hyperparameter selected for the optimization process. First, it is important to identify the specific ML algorithm for which the hyperparameters need optimization to produce the best performance. The easy way is to read the documentation of the selected ML algorithm. For example, sklearn’s random forest algorithm has about 18 hyperparameters that can be combined. You can find its documentation provided by the scikit-learn library.

Examples of hyperparameters from the random forest algorithm are as follows:

n_estimators: This is the number of trees in the forest.

criterion: This is the function to measure the quality of a split.

max_depth: This is the maximum depth of the tree.

min_sample_split: This represents the minimum number of samples required to split an internal node.

max_features : This is the number of features to consider when looking for the best split.

2. Create a grid of all possible combinations of hyperparameter values
The second step is to create a grid of possible combinations of values for each hyperparameter. This can be done by specifying a range of values or a set of discrete values. For example, n_estimators and criterion from the random forest algorithm can have a range of values as follows:

n_estimators = [50,100,250]

criterion= ["gini", "entropy", "log_loss"]

With these two hyperparameters, we can have a total of nine combinations of hyperparameters for the optimization process. These combinations are (50, "gini"), (50, "entropy"), (50, "log_loss"), (100, "gini"), (100, "entropy"), (100, "log_loss"), (250, "gini") , and (250, "entropy"), (250, "log_loss"). Keep in mind that the more hyperparameters and their values we add, the more combinations of hyperparameters we create for the optimization process.

3. Train a model using every possible combination of hyperparameter values 
In this step, the grid search method will use every possible combination of hyperparameters to train the ML model on the training data. This process will be repeated for the rest of the possible combinations of hyperparameter values. For example, if there are nine possible combinations of hyperparameters, then the grid search method will train a total of nine ML models.

4. Evaluate and record the performance of the ML model
The performance of each trained model will be evaluated on the validation data using a specified evaluation metric based on the ML problem (classification or regression). When working on the ML project for classification problems, it is recommended to use the following evaluation metrics:

Accuracy: This is the number of correct predictions from an ML model divided by the total number of predictions made.

F1 score: This is the harmonic mean of precision and recall.

If the ML project focuses on solving regression problems, it is recommended to use the following evaluation metrics:

Mean absolute error (MAE): This is the absolute value of the difference between the predicted value and the actual value.

Root mean squared error (RMSE): This is the square root of the value calculated from the mean square error (MSE).

Finally, the grid search method will record the performance of the ML model for each possible combination of hyperparameters based on the evaluation metric specified.

5. Select the best-performing combination of hyperparameters
After going through all possible combinations of hyperparameters, the grid search method will select the combination of hyperparameters that results in the best performance according to the evaluation metric used in   Step 4.

![image](https://github.com/user-attachments/assets/1e6c3aae-bac5-4fef-8b3b-2373144da6f4)

6. Train the final ML model with selected hyperparameters
The final step is to train the final ML model using the best combination of hyperparameters identified in Step 5. The final model will be trained on the full training data and the validation data. This will be the final ML model that will be used to make predictions on new or unseen data.

These are the important steps that a grid search method must follow to find the best combination of hyperparameters for optimizing ML performance. Since it will train all possible combinations of hyperparameters, this method will be computationally expensive, especially if the number of hyperparameters or the range of values for each parameter is large.

## Example Implementation : Binary Classification problem statement is optimized using Grid Search CV on Logistic Regression and Random Forest Algorithm

