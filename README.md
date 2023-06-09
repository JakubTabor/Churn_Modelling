# Churn_Modelling
# First I "drop" useless "columns" """df.drop(['CustomerId', 'RowNumber', 'Surname'], axis='columns', inplace=True)"""
# Then I change "Gender" "column" into "numerical values" """df['Gender'].replace({'Female': 1, 'Male': 0}, inplace=True)""" 
# And check unique values "df['Gender'].unique()"
# I also need to change my "column" "Geography" into numerical values and create (3) different columns, because they don't have any dependence
# I use method "get_dummies" on my "column" """df = pd.get_dummies(data=df, columns=['Geography'])"""
# Then I need to "scale" my "columns" with big "values", so I import "MinMaxScaler"
# Now I prepare my "columns to scale" """col_to_scale = ['Balance', 'EstimatedSalary', 'CreditScore', 'Age', 'Tenure', 'NumOfProducts']"""
# Next I use my "scaler" and "fit_transform" method on this "columns" """sc.fit_transform(df[col_to_scale])""" and save it as """df[col_to_scale]"""
# I check "Imbalance Ratio" of my "Exited" "column", so I use "value_counts" on "Exited" and save it as "class_distribution"
# I get value (0) and (1) which belong to "column" "Exited" and save it as "imbalance_ratio" """class_distribution[0] / class_distribution[1]"""
# Then I print "Imbalance Ratio" rounding to 1 decimal place """print('Imbalance Ratio:', np.round(imbalance_ratio, 1))"""
# Now when I have "Imbalance Ratio" I also check numbers of my "Exited" "columns" """count_class_0, count_class_1 = df.Exited.value_counts()"""
# I save my (2) classes as "df_class_0" and "df_class_1"  """df[df['Exited']==0] | df[df['Exited']==1]"""
# And I check if there is any (0) values """df.isnull().sum().sum()"""
# Now I use "pd.concat" to unite my two classes """pd.concat([df_class_0.sample(count_class_1), df_class_1], axis=0)""" and I save it as "df_test_under"
# Then I check "value number" of my "df_test_under" """df_test_under.Exited.value_counts()"""
# I prepare "X" as data without "Exited" column """df.drop('Exited', axis='columns')""" and "y" as "Exited" """y = df['Exited']"""
# And get "train" and "test" set using "train_test_split" and I check their "shape" "X_train.shape" "X_test.shape"
# Now I can create and supplement my model, so I import "tensorflow", "keras" and create "keras.Sequential"
# First "layers" have (26) neurons and "input_shape=(12,)" because i have (12) columns in my data, the best "activation" is "relu", so I use it
# """keras.layers.Dense(26, input_shape=(12,), activation='relu')""" I also drop half of my neurons after every run, to deel with overfit
# My hidden layer have (15) neurons and also "activation "relu" I use "Dropout" to drop neurons """keras.layers.Dropout(0.5)"""
# And the last must have (1) output neuron and in that case the best "activation" is "sigmoid" """keras.layers.Dense(1, activation='sigmoid')"""
# Then I gonna "compile" my "model" with the best "optimizer" "adam", I have "binary" output, so I use as loss "binary_crossentropy"
# And my "metrics" will be "accuracy", Then i train my "model", set numbers of "epochs" at (50) and my "batch gradient descent" at (8)
# I "evaluate" my model and get pretty good score """model.evaluate(X_test, y_test)"""
# Now I get "y_pred" and reshape "predictions" into one dimension array """y_pred = model.predict(X_test).reshape(-1)"""
# I also "round" my score """np.round(y_pred)""" and I check compatibility of my predictions
# Finally I get "classification report" and check parameters "f1-score" is the most import, it seems that my data is imbalanced
