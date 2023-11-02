#NAAN MUTHALVAN 

Drive link-phase1 

https://drive.google.com/file/d/1Ns1gpjVcUDZr0n5H2rYNjwAW4GHRIndY/view?usp=drivesd# 

Drive link-phase 2 

https://drive.google.com/file/d/1UW5dc7ZViQsaF5Iov9MrNKfAw987RKIB/view?usp=drivesdk

Drive link-phase 3 

https://drive.google.com/file/d/1Z1TvsaGvsxkRlPub62hKm7qT1cOBid3m/view?usp=drivesdk

Drive link-phase 4

https://drive.google.com/file/d/1dR8U-VIdkV32JUnrUn5zhY05ing1SLzi/view?usp=drivesdk

Drive link-phase 5

https://drive.google.com/file/d/1ijTkERmjt-TR0x0ddAjyzTGZzcDwANPL/view?usp=drivesdk


Summary:

   The project on "Air Quality Analysis and Prediction in Tamil Nadu" aims to develop a predictive model to assess and forecast air quality parameters by utilizing historical and real-time data. The project involves multiple key components

Objectives:
Problem Identification:
-  Addressing the challenges posed by air pollution in Tamil Nadu due to various factors such as industrialization, urbanization, and environmental conditions.

Data Utilization
- Utilizing diverse datasets containing air quality parameters, meteorological data, and geographical information to build a predictive model.
  
Prediction and Mitigation:
- Developing a machine learning-based model to predict air quality levels and contributing to strategies for better environmental management and public health improvement.
  
Methodology:
 Design Thinking Approach:
 - Employing a user-centered and iterative design thinking process to empathize, define, ideate, prototype, test, implement, and iterate through the development phases.
  
Data Preprocessing:
 - Cleaning, handling missing values, and scaling the dataset to ensure data quality and uniformity for modeling.

Exploratory Data Analysis:

 - Analyzing data through statistics, visualizations, and correlations to understand underlying patterns and relationships between variables.
   
Machine Learning Model Development:

 - Selecting appropriate algorithms and developing models to predict air quality parameters based on historical and current data.

 Deliverables:
 Code and Model Development:

 - Providing Python-based scripts and programs for data preprocessing, exploratory data analysis, model development, and evaluation.

 Documentation:

 - Offering detailed documentation outlining problem statements, design thinking approach, dataset description, preprocessing steps, model selection, and innovative techniques applied during the development.

Program:

import pandas as pd
import matplotlib.pyplot as plt
 Load the dataset
data = pd.read_csv('air_quality_data.csv')
Basic statistics and information about the dataset
print(data.head()) 

Display the first few rows
print(data.describe())

Summary statistics of numerical columns
print(data.info())  
Information about the dataset

 Visualizations for exploratory analysis
Example: Plotting histograms for air quality parameters
data.hist(bins=20, figsize=(12, 10))
plt.suptitle('Air Quality Parameters Histograms')
plt.show()

Example: Line plot to visualize trends over time (if time-related column is present)
if 'Date' in data.columns:

Change'Date' to the actual column name containing the date
    data['Date'] = pd.to_datetime(data['Date'])
    Convert 'Date' to datetime if not already
    data.set_index('Date', inplace=True) 
    Set 'Date' as index for time-series visualization
    data.plot(figsize=(12, 6))
    plt.title('Air Quality Trends Over Time')
    plt.xlabel('Date')
    plt.ylabel('Air Quality Parameter Values')
    plt.legend(loc='best')
    plt.show()
else:
    print("Date column not found for time-series visualization.")

 Correlation matrix heatmap
correlation_matrix = data.corr()
plt.figure(figsize=(10, 8))
plt.title('Correlation Heatmap')
plt.imshow(correlation_matrix, cmap='coolwarm', interpolation='nearest')
plt.colorbar()
plt.xticks(ticks=range(len(correlation_matrix.columns)), labels=correlation_matrix.columns, rotation=90)
plt.yticks(ticks=range(len(correlation_matrix.columns)), labels=correlation_matrix.columns)
plt.show()
import pandas as pd
 Load the dataset
data = pd.read_csv('your_dataset.csv')   Replace 'your_dataset.csv' with your actual dataset file

Handling missing values
data.fillna(method='ffill', inplace=True)  
Forward-fill missing values

Removing duplicates if any
data.drop_duplicates(inplace=True)

Outlier detection and handling (assuming RSPM/PM10, SO2, NO2 are columns)
def remove_outliers(df, column):
    Q1 = df[column].quantile(0.25)
    Q3 = df[column].quantile(0.75)
    IQR = Q3 - Q1
    lower_bound = Q1 - 1.5 * IQR
    upper_bound = Q3 + 1.5 * IQR
    df = df[(df[column] > lower_bound) & (df[column] < upper_bound)]
    return df

data = remove_outliers(data, 'RSPM/PM10')
data = remove_outliers(data, 'SO2')
data = remove_outliers(data, 'NO2')

Format or preprocess data further if needed (e.g., date parsing, feature engineering)

Save preprocessed data to a new CSV file
data.to_csv('preprocessed_data.csv', index=False)
