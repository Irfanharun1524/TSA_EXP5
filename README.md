# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 20-08-2026


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Read the CSV file
df = pd.read_csv(r"C:\Users\admin\Downloads\bmw (1).csv")

# Display first five rows
print("FIRST FIVE ROWS:")
print(df.head())

# Select price as the time series
data = df["price"].dropna()

# Plot original data
plt.figure(figsize=(12, 5))
plt.plot(data)
plt.title("BMW Car Price Data")
plt.xlabel("Observation")
plt.ylabel("Price")
plt.show()

# Seasonal decomposition
result = seasonal_decompose(data, model="additive", period=12)

# Seasonal plot
plt.figure(figsize=(12, 5))
plt.plot(result.seasonal)
plt.title("SEASONAL PLOT REPRESENTATION")
plt.xlabel("Observation")
plt.ylabel("Seasonal Component")
plt.show()

# Trend plot
plt.figure(figsize=(12, 5))
plt.plot(result.trend)
plt.title("TREND PLOT REPRESENTATION")
plt.xlabel("Observation")
plt.ylabel("Trend")
plt.show()

# Overall decomposition
result.plot()
plt.suptitle("OVERALL REPRESENTATION", fontsize=14)
plt.tight_layout()
plt.show()
```
### OUTPUT:
FIRST FIVE ROWS:

<img width="878" height="246" alt="image" src="https://github.com/user-attachments/assets/72ee6e83-600d-4e9b-a0b7-94aff4e7797e" />

PLOTTING THE DATA:

<img width="1006" height="443" alt="image" src="https://github.com/user-attachments/assets/dad4f855-6215-40ea-814f-7e7083264007" />


SEASONAL PLOT REPRESENTATION :

<img width="1022" height="443" alt="image" src="https://github.com/user-attachments/assets/346be60e-4810-410b-9969-3e746ff13367" />


TREND PLOT REPRESENTATION :

<img width="1025" height="448" alt="image" src="https://github.com/user-attachments/assets/89b9c7cc-b5a4-4cb6-83cf-af5776f0222f" />


OVERAL REPRESENTATION:

<img width="722" height="500" alt="image" src="https://github.com/user-attachments/assets/684548b7-9187-4714-b4cc-0ea7e384a436" />


### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
