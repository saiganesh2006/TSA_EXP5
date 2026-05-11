# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 11-05-2026


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

# Import necessary modules
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Step 1: Load dataset
data = pd.read_csv('dataset.csv')
print(data.head())
# Step 2: Take samples from 0 to 100
data = data.iloc[0:100]

# Step 3: Create index
data.index = range(len(data))

# Step 4: Perform seasonal decomposition
decomposition = seasonal_decompose(
    data['temp_mean(c)'],
    model='additive',
    period=24
)

# Step 5: Plot graphs
plt.figure(figsize=(10, 12))

# Original Data
plt.subplot(411)
plt.plot(data['temp_mean(c)'])
plt.title('Original Data')

# Trend
plt.subplot(412)
plt.plot(decomposition.trend, color='orange')
plt.title('Trend Plot')

# Seasonal
plt.subplot(413)
plt.plot(decomposition.seasonal, color='green')
plt.title('Seasonality Plot')

# Residual
plt.subplot(414)
plt.plot(decomposition.resid, color='red')
plt.title('Residual Plot')

plt.tight_layout()
plt.show()
```














### OUTPUT:
FIRST FIVE ROWS:

<img width="668" height="276" alt="image" src="https://github.com/user-attachments/assets/06f1612c-341a-41a7-83eb-2b92ca689207" />


ORIGINAL TIME SERIES DATA:
<img width="1172" height="337" alt="image" src="https://github.com/user-attachments/assets/fa4a8272-7e87-4696-809f-ed2ff06723f1" />


TREND PLOT :
<img width="1197" height="338" alt="image" src="https://github.com/user-attachments/assets/14e0cb07-91d0-43d1-a1f4-ba675042dcb2" />

SEASONAL PLOT :

<img width="1205" height="346" alt="image" src="https://github.com/user-attachments/assets/53671451-8c95-4f94-b378-63981d2421a2" />


RESIDUAL PLOT:

<img width="987" height="273" alt="image" src="https://github.com/user-attachments/assets/704fecc8-095b-41ef-adf9-de5db58bc140" />

### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
