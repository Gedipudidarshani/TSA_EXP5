# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 02-09-2025
#### NAME:GEDIPUDI DARSHANI
#### REGISTER NUMBER:212223230062

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

# Step 1: Load the dataset, Convert 'date' column to datetime format, Set it as index
data = pd.read_csv('INDIA.csv', parse_dates=['date'], index_col='date')

# Step 2: Perform seasonal decomposition using the correct column name
decomposition = seasonal_decompose(data['open'], model='additive', period=12)

# Step 3: Plot the decomposition
plt.figure(figsize=(10, 12))  # Adjust the figure size

# Original Data
plt.subplot(411)
plt.plot(data['open'], label='open')
plt.legend(loc='upper left')
plt.title('Open Prices')

# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Trend')

# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality')

# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residuals')

plt.tight_layout()
plt.show()

```

### OUTPUT:

PLOTTING THE DATA:
<img width="1204" height="380" alt="image" src="https://github.com/user-attachments/assets/411d6c6d-9411-4906-bb70-f2ae5a15a135" />
LINEAR TREND PLOT:
<img width="1216" height="377" alt="image" src="https://github.com/user-attachments/assets/5e3709cb-7145-4a76-8c0d-47f779688f5e" />

SEASONAL PLOT REPRESENTATION :
<img width="1230" height="370" alt="image" src="https://github.com/user-attachments/assets/1f95a561-d5c6-489f-be38-5de81896140f" />

RESIDUAL PLOT:
<img width="1223" height="373" alt="image" src="https://github.com/user-attachments/assets/ccf0e186-32a0-4abd-84c9-562e7feecaaa" />


### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
