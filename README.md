### Developed by: Anbuselvan S
### Register No: 212223240008
### Date:

# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION OF YAHOO STOCK PREDICTION.

## AIM:
To Illustrates how to perform time series analysis and decomposition of the yahoo stock prediction.

## ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

## PROGRAM:
```
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

data = pd.read_csv('/content/yahoo_stock.csv', parse_dates=['Date'], index_col='Date')

result = seasonal_decompose(data['Volume'], model='additive', period=12)  

print("FIRST FIVE ROWS:")
print(data.head())

plt.figure(figsize=(8, 4))
plt.plot(data, label='Original Data')
plt.title('PLOTTING THE DATA')
plt.xlabel('Date')
plt.ylabel('Value')
plt.legend()
plt.tight_layout()
plt.show()

result.plot()
plt.show()

trend = result.trend
seasonal = result.seasonal
residual = result.resid

print("Trend:\n", trend)
print("Seasonal:\n", seasonal)
print("Residual:\n", residual)
```

## OUTPUT:

### FIRST FIVE ROWS:
![image](https://github.com/user-attachments/assets/6b198cad-9982-460a-af69-810af7924bda)

### PLOTTING THE DATA:
![image](https://github.com/user-attachments/assets/92d28a41-fa1a-4792-a4e5-38e713686fe9)

### OVERAL REPRESENTATION:
![image](https://github.com/user-attachments/assets/96476f16-c26d-45bf-84c8-e55770547cae)

### RESULT:
Thus, the python code for the time series analysis and decomposition of yahoo stock prediction is successful.
