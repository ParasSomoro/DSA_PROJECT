# DSA_PROJECT

1)	Pick Dataset.
https://www.kaggle.com/datasets/fedesoriano/traffic-prediction-dataset
2)	There are Three questions. And how the data could be used.

What are the different features or columns available in the dataset?
How is missing data handled in this dataset, if at all?
What is the data type of each feature (e.g., numerical, categorical, datetime)?







1)	import pandas as pd 

# Replace 'your_dataset.csv' with the actual path to your dataset file
data = pd.read_csv('traffic.csv')

# Get the list of column names
columns = data.columns

# Display the column names
print(columns)
     
Index(['DateTime', 'Junction', 'Vehicles', 'ID'], dtype='object')
2)

import pandas as pd

# Replace 'your_dataset.csv' with the actual path to your dataset file
data = pd.read_csv('traffic.csv')

# Check for missing values in each column
missing_data = data.isnull().sum()

# Display columns with missing values (if any) and the count of missing values
columns_with_missing_data = missing_data[missing_data > 0]

# If you want the percentage of missing values in each column, you can calculate it like this:
percentage_missing_data = (missing_data / len(data)) * 100

# Display columns with missing values and their corresponding percentage of missing data
columns_with_percentage_missing = percentage_missing_data[percentage_missing_data > 0]

# Print the results
print("Columns with missing data:")
print(columns_with_missing_data)

print("\nColumns with percentage of missing data:")
print(columns_with_percentage_missing)

     
Columns with missing data:
Series([], dtype: int64)

Columns with percentage of missing data:
Series([], dtype: float64)
3)
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Replace 'your_dataset.csv' with the actual path to your dataset file
data = pd.read_csv('traffic.csv')

# Calculate the correlation matrix
correlation_matrix = data.corr()

# Create a heatmap to visualize the correlations
plt.figure(figsize=(12, 8))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', fmt=".2f")
plt.title('Correlation Matrix')
plt.show()

     
<ipython-input-10-f6072d5fbf01>:9: FutureWarning: The default value of numeric_only in DataFrame.corr is deprecated. In a future version, it will default to False. Select only valid columns or specify the value of numeric_only to silence this warning.
  correlation_matrix = data.corr()
 

