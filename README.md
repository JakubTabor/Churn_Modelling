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
