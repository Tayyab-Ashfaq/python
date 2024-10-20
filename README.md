Summary and Recommendations
Objective: 
The analysis primarily investigates factors influencing customer churn, particularly focusing on payment methods and contract types.
I would be glad to provide a comprehensive guide on data cleaning that I performed in Python Pandas, project incorporating best practices and addressing potential issues:
Basic information:
10000 rows data
There are 21 columns with 19 features
Target: The “Churn” column is our target
1. Import Necessary Libraries:
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
2. Load Data:
df = pd.read_csv('/content/Churn_Modelling.csv')
Handle Missing Values:
To handle missing values we apply four techniques first of all by deleting the columns not required for processing, by deleting the rows with missing data, filling the missing values with zeros and forward and backward filling. There are only 11 missing values, all of them for the TotalCharges column. These values are actually a blank space in the csv file and are exclusive for customers with zero tenure. So we will impute this missing values with zero. We are trying to predict if the client left the company in the previous month. Therefore we have a binary classification problem with a slightly unbalanced target: Churn: No - 72.4% and Churn: Yes - 27.6%. We can see our data is highly imbalanced, ratio = 73:27
Handle duplicates:
Check for duplicate rows and remove them: 
df.duplicated ( )
df.drop_duplicates ( )
Outlier Detection and Removal
Handle outliers:
•	Remove: If outliers are deemed irrelevant, remove them.
•	Cap: Replace outliers with extreme values within a reasonable range.
•	Transform: Apply transformations like log or square root to normalize the data
Transforming Data
Convert data types: Convert data to appropriate data types (e.g., numeric, categorical, date)
Normalize data: Scale numerical features to a common range (e.g., using min-max scaling or standardizatio
new_df['Age']=new_df['Age'].fillna(new_df['Age'].mean())
new_df.info()
scaler = MinMaxScaler()
normalized_df=scaler.fit_transform(new_df)
print(normalized_df)
Saving Cleaned Data:
After cleaning, save the processed data for further analysis using to_csv() or other formats
df = pd.read_csv('/content/Churn_Modelling.csv')
Through these steps we achieve a clean, well-structured dataset ready for analysis or modeling.
Descriptive statistics for multiple columns:
Descriptive statistics provide a concise overview of the data distribution. By analyzing the count, mean, median we can detect missing values, and errors in the dataset. 
Visualization: 
The visualizations, including bar plots and line graphs, highlight the disparity in churn rates by different contract types and payment methods. They also show trends over customer tenure, supporting the need for personalized retention strategies. In histogram plot we analyzed distribution of customer tenure and pie chart give us percentage of churn customers.
Conclusion:
Data cleaning and visualization is a crucial step in data analysis and machine learning. It involves identifying and correcting errors, inconsistencies, or missing values in a dataset to ensure its quality and reliability. By addressing these key areas (Payment Method, Long-Term Contract, Retention Program), the company can significantly reduce customer churn. These findings also help us to clean and prepare the data and lay the foundation for further analysis.
Recommendations:
 Promote Long-Term Contracts: Offer incentives for customers to commit to longer contracts to reduce churn.
Address Payment Method Concerns: Implement campaigns encouraging customers to switch from electronic checks to more reliable payment methods
#AinGenx #Python #DataAnalysis

