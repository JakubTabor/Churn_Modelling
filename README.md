# Churn_Modelling
# First I "drop" useless "columns" """df.drop(['CustomerId', 'RowNumber', 'Surname'], axis='columns', inplace=True)"""
# Then I change "Gender" "column" into "numerical values" """df['Gender'].replace({'Female': 1, 'Male': 0}, inplace=True)""" 
# And check unique values "df['Gender'].unique()"
# I also need to change my "column" "Geography" into numerical values and create (3) different columns, because they don't have any dependence
