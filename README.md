# deep-learning-challenge

1. Overview
In this analysis, we're tackling the challenge of predicting whether charities funded by Alphabet Soup will succeed. The goal is to build and evaluate a deep learning model that can classify these organizations based on their attributes.

2. Data Preprocessing
2.1 Identifying Targets and Features
Target Variable: We're predicting the success of the charity, so that's our target.
Feature Variables: Our features include various attributes of the organizations, like their application type, classification, and income.
Removed Variables: We dropped irrelevant columns like EIN and NAME since they don't add any predictive value.
2.2 Handling Categorical Variables
We examined the categorical variables (APPLICATION_TYPE and CLASSIFICATION) to see how often different categories appeared.
To simplify the model, we combined less common categories into an "Other" category.
Then, we converted these categorical variables into a numeric format using pd.get_dummies() so that the model could work with them.
2.3 Data Splitting and Scaling
We split the data into training and testing sets, with 80% for training and 20% for testing.
To ensure the model trains efficiently, we scaled the features using StandardScaler. This step helps to standardize the range of the data, which is crucial for neural networks.
3. Model Design and Training
3.1 Model Architecture
Input Layer: We started with an input layer that matched the number of features in our dataset.
Hidden Layers: We added two hidden layers—one with 80 neurons and another with 30—both using the ReLU activation function, which is a good default for most problems.
Output Layer: The output layer used a sigmoid activation function to produce a probability for the binary classification.
3.2 Model Compilation
We compiled the model using the Adam optimizer, which is known for being both fast and reliable. We used binary cross-entropy as our loss function since we’re dealing with a binary classification problem, and accuracy as our metric to track how well the model performs.
3.3 Model Training
The model was trained for 100 epochs, with the training and validation accuracy being monitored to see how the model performed as it learned.
4. Results
4.1 Data Preprocessing
Target Variable: The goal was to predict whether a charity would be successful.
Feature Variables: All relevant columns after dropping EIN and NAME.
Removed Variables: EIN and NAME were excluded as they didn’t contribute to the predictions.
4.2 Model Design
Neurons and Activation Functions: We chose 80 neurons for the first hidden layer and 30 for the second, with ReLU as the activation function. The output layer used sigmoid for binary classification.
Performance: The model didn’t hit the accuracy target, leveling out at about 53.4%.
4.3 Optimization Attempts
We tried various tweaks, like adjusting the number of neurons, layers, and activation functions, but the model’s accuracy still plateaued.
We considered early stopping to avoid overfitting, but the validation accuracy remained stuck around the same level.
5. Summary and Recommendations
5.1 Model Performance
Our neural network didn’t reach the desired accuracy, hovering around 53.4%. The high loss values in the early epochs suggest the model struggled to learn effectively.
5.2 Potential for Different Models
Recommendation: We could try a different approach, like using a Random Forest or Gradient Boosting Machine. These models might do a better job with the categorical data and could provide better performance by handling the data’s complexity more naturally.
Why These Models? Tree-based models like Random Forests and Gradient Boosting are great at capturing non-linear relationships and are less sensitive to data scaling, making them a good alternative to explore.
6. Conclusion
Even though our neural network didn’t hit the accuracy mark we were aiming for, the process was insightful. Moving forward, trying out different models and refining the features could help improve the predictions.
