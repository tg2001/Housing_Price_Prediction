# Observations:

It can be seen that few lines of code were commented out in the notebook. They were used to draw some observaions, which are:
- The dataset is very scattered and contains many outliers (as can be seen from the graph), which could affect the models accuracy.
To reduce the effect of outliers, Standard Scaler was used instead of MinMaxScaler. Also the null entries were replaced by the median of the columns instead of removing it.
- The dataset contains columns like total number of rooms, total number of bedrooms, households, etc; 
but it could have contained more meaningful data like number of rooms per household, number of bedrooms per household, etc. 
Thus they were added. But it was observed that they basically degraded the models performance (unexpected). So they were removed (i.e., commented out).
- Each column was removed one at a time to see which column affected the model's accuracy the most.
- It was seen that the median_income affected the model the most (as expected), followed by Longitude and Latitude. 
So their squares were also added as columns in the dataset to give some extra weightage to those columns, but it didn't bring in much change.
- Basic ML models like Linear Regression and SVM were also tested out, but the results were very bad (indicated by their rmse). So ANN was used.
- Many different types of models were tested out like a model with 1, 2, 3, 4 and 5 hidden layers, model with one or more batch normalization layers, layers with different activation
functions, layers with different numbers of neurons, etc.
- The model's accuracy improved when 1 hidden layer was replaced with 2 and 2 was replaced with 3. But on further increasing the numberof hidden layers, 
no significant change was seen. 
- Also increasing the number of neurons per hidden layer improved accuracy, but the improvement was getting smaller and smaller.
The current number of hidden layer seemed to be reasonable w.r.t to the improvement in accuracy.
- Using dfiferent activation functions didn't bring about any significant change; neither did the addition of batch normalization layer.
- Adam Optimizer was used because SGD optimizer didn't work for regression.
- Callbacks like Early Stopping and ReduceLROnPlateau worked well with model.
- Inspite of all these, the models rmse was as high as 55k (May be beacuse of the scattered dataset)

# Possible Improvements:

Some possible improvement to all these can be:
- Better data cleaning and data preprocessing steps may help in improving model accuracy (like outliers removal)
- Better algorithms and optimizers might also help. (Though the first point seems to be more promising)
