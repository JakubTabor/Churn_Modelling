# Churn_Modelling
# First I "drop" useless "columns" """df.drop(['CustomerId', 'RowNumber', 'Surname'], axis='columns', inplace=True)"""
# Then I change "Gender" "column" into "numerical values" """df['Gender'].replace({'Female': 1, 'Male': 0}, inplace=True)""" 
# And check unique values "df['Gender'].unique()"
# I also need to change my "column" "Geography" into numerical values and create (3) different columns, because they don't have any dependence
# I use method "get_dummies" on my "column" """df = pd.get_dummies(data=df, columns=['Geography'])"""
# Then I need to "scale" my "columns" with big "values", so I import "MinMaxScaler"
# Now I prepare my "columns to scale" """col_to_scale = ['Balance', 'EstimatedSalary', 'CreditScore', 'Age', 'Tenure', 'NumOfProducts']"""
