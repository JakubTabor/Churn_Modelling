# Churn_Modelling
# First I "drop" useless "columns" """df.drop(['CustomerId', 'RowNumber', 'Surname'], axis='columns', inplace=True)"""
# Then I change "Gender" "column" into "numerical values" """df['Gender'].replace({'Female': 1, 'Male': 0}, inplace=True)""" 
