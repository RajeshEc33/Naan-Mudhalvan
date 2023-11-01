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
Load the dataset
 data =  pd.read_csv('air_quality_data.csv')

Checking for missing values
 missing_values = data.isnull().sum()
print("Missing Values:")
print(missing_values)

Handling missing values (this is a simple example)
    Replace missing values in SO2, NO2, and RSPM/PM10 columns with their means
 data['SO2'].fillna(data['SO2'].mean(), inplace=True)
data['NO2'].fillna(data['NO2'].mean(), inplace=True)
data['RSPM/PM10'].fillna(data['RSPM/PM10'].mean(), inplace=True)

Data normalization (scaling the data to a common range)
from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()
data[['SO2', 'NO2', 'RSPM/PM10']] = scaler.fit_transform(data[['SO2', 'NO2', 'RSPM/PM10']])

 Feature selection (in this example, all columns except 'Location' are used as features)
features = data.drop('Location', axis=1)

 You can proceed with further analysis, visualization, or model development using the 'features' DataFrame
 
 For example, performing exploratory data analysis, building predictive models, or generating visualizations.

Save the preprocessed data to a new CSV file if needed
data.to_csv('preprocessed_air_quality_data.csv', index=False)
