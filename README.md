# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 06/09/2025

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

data['Timestamp'] = pd.to_datetime(data['Timestamp'])

plt.figure(figsize=(10,5))
plt.plot(data['Timestamp'], data['Close'], label="Close Price")
plt.xlabel("Timestamp")
plt.ylabel("Close Price")
plt.title("Bitcoin Close Price Over Time")
plt.legend()
plt.show()

# First order differencing
data['Close'] = pd.to_numeric(data['Close'], errors='coerce')
data_diff = data['Close'].diff().dropna()

plt.figure(figsize=(10,5))
plt.plot(data['Timestamp'].iloc[-len(data_diff):], data_diff, label="Regular Differencing")
plt.xlabel("Timestamp")
plt.ylabel("Differenced Close Price")
plt.title("Bitcoin Close Price - Regular Differencing")
plt.legend()
plt.show()

# Seasonal Adjustment (Seasonal Differencing)

# Assuming daily data, a seasonal period of 365 might be more appropriate,
# but using 12 for demonstration as in your example.
# You might need to adjust the period based on the actual seasonality of your data.
data['Close'] = pd.to_numeric(data['Close'], errors='coerce')
data_seasonal_diff = data['Close'].diff(12).dropna()

plt.figure(figsize=(10,5))
plt.plot(data['Timestamp'].iloc[-len(data_seasonal_diff):], data_seasonal_diff, label="Seasonal Differencing (lag=12)")
plt.xlabel("Timestamp")
plt.ylabel("Seasonally Differenced Close Price")
plt.title("Bitcoin Close Price - Seasonal Differencing (lag=12)")
plt.legend()
plt.show()

# Log Transformation
data['Close'] = pd.to_numeric(data['Close'], errors='coerce')
data_log = np.log(data['Close'])

plt.figure(figsize=(10,5))
plt.plot(data['Timestamp'], data_log, label="Log Transformed")
plt.xlabel("Timestamp")
plt.ylabel("Log of Close Price")
plt.title("Bitcoin Close Price - Log Transformation")
plt.legend()
plt.show()


```


### OUTPUT:


REGULAR DIFFERENCING:<img width="1090" height="582" alt="image" src="https://github.com/user-attachments/assets/956fd2ad-4bae-4b69-8b03-0948e59b5013" />



SEASONAL ADJUSTMENT:<img width="1090" height="578" alt="image" src="https://github.com/user-attachments/assets/e45dd3b7-5cb4-4daa-a5a5-e5bb59e6268e" />



LOG TRANSFORMATION:<img width="1039" height="579" alt="image" src="https://github.com/user-attachments/assets/fee4e847-37a3-4b82-b51f-d0b5ea6c4d9c" />




### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
