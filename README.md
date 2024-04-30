# Intern-Assignment
The repository contains zip file with name files.zip. The files.zip has 4 sets of csv file.
1) test.csv --> test_label.csv
2) smap_test.csv --> smap_test_labels.csv
3) msl_test.csv --> msl_test_labels.csv
4) psm_test.csv --> psm_test_labels.csv

   test.csv files have multivariate time series data and test_labels.csv labels files have time stamps of anomaly regions.
   Write python code for the following tasks
   
   a) Read test and label files
   b) Draw time series plots with anomaly regions 
   c) Perform EDA and find out root cause
   d) Find out the variables which are the root cause for the anomaly
   import pandas as pd
import matplotlib.pyplot as plt

# a) Read test and label files
def read_files(test_file, label_file):
    test_data = pd.read_csv(test_file)
    label_data = pd.read_csv(label_file)
    return test_data, label_data

# b) Draw time series plots with anomaly regions
def plot_with_anomalies(test_data, label_data):
    plt.figure(figsize=(15, 5))
    for column in test_data.columns:
        plt.plot(test_data[column], label=column)
    
    # Highlight anomaly regions
    for index, row in label_data.iterrows():
        plt.axvspan(row['start'], row['end'], color='red', alpha=0.3)
    
    plt.legend()
    plt.show()

# c) Perform EDA to find out root cause
# This is a placeholder for your exploratory data analysis process.
# You might want to look at statistical summaries, correlations, or perform
# other analyses to understand the data better.

# d) Find out the variables which are the root cause for the anomaly
# This is a complex task that typically involves domain knowledge and
# possibly machine learning models to determine. You might want to use
# feature importance from models like Random Forest, or look at correlation
# with the anomaly labels.

# Example usage:
test, test_labels = read_files('test.csv', 'test_label.csv')
plot_with_anomalies(test, test_labels)

# For EDA and finding root cause variables, you would need to conduct
# specific analyses based on the nature of your data and the domain.


