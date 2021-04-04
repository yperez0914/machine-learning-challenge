# machine-learning-challenge

For this project, I created two machine learning models to predict new exoplanets. There were 3 steps to the process:<br>
1. Preprocessing the data
2. Tuning the models
3. Comparing two or models
<br>
# Preprocessing the data <br>
When preprocessing the data, columns that were not numeric values were dropped including: 'rowid', 'kepid', 'kepoi_name', 'kepler_name', 'koi_disposition', and 'koi_tce_delivname'. The decision needed to be made whether to drop koi_disposition or koi_pdospition. The first time through, I used koi_disposition as my targer. However, since it had three possible values, the model could not reach convergence resulting in accuracy scores of less than 50% before hyptertuning and less than 60% with hyptertuning. Therefore, in my final notebook, koi_pdisposition is instead used as the target and koi_disposition is dropped. Data is split into training and testing data. I then used the MinMaxScaler to fit the data. <br>
<br>
# Tuning the Models <br>
To make predictions, the LogisticRegression model (solver = liblinear) as well as the SVC model(kernel = rbf). When using the LogisticRegression model, I used classifier.score to generate predictions based on the training and testing data. The predictions were less than 50% accurate. However, when I then used the GridSearch estimator, the best grid score was .99 and the resulting test accuracy was 96%.<br>

When using the SVC model, I used model.predict to generate predictions based on the training and testing data. The resulting accuracy was 70%. I then used the GridSearch estimator.  The best grid score was also .99. However, when making predictions using the hyptertuned model, the accuracy dropped to 48% as no "candidate" values appeared in the fitted grid data. <br>
<br>
# Comparing two or models<br>
The LogisticRegression model hypertuned with a GridSearch estimator, therefore, is the best model to use to predict new exoplanets as it resulted in the highest percent accuracy- 96%, when using the koi_pdisposition as the target. <br>

