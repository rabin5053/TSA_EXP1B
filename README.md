
# Ex.No: 1B CONVERSION OF NON STATIONARY TO STATIONARY DATA
Date:21-04-2025

# AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data

#  ALGORITHM:
1.Import the required packages like pandas and numpy
2.Read the data using the pandas
3.Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4.Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5.Display the overall results.

# PROGRAM:
```



import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Load the data
data = pd.read_csv("AirPassengers.csv")
# Create DataFrame
df = pd.DataFrame(data)

# Regular differencing
df['Regular Difference'] = df['#Passengers'].diff()

# Seasonal adjustment
result = seasonal_decompose(df['#Passengers'], model='additive', period=12)
df['Seasonal Adjustment'] = result.resid

# Log transformation
df['Log Transformation'] = np.log(df['#Passengers'])

# Plotting
plt.figure(figsize=(14, 10))

plt.subplot(4, 1, 1)
plt.plot(df['#Passengers'], label='Original')
plt.legend(loc='best')
plt.title('Original Data')

plt.subplot(4, 1, 2)
plt.plot(df['Regular Difference'], label='Regular Difference')
plt.legend(loc='best')
plt.title('Regular Differencing')

plt.subplot(4, 1, 3)
plt.plot(df['Seasonal Adjustment'], label='Seasonal Adjustment')
plt.legend(loc='best')
plt.title('Seasonal Adjustment')

plt.subplot(4, 1, 4)
plt.plot(df['Log Transformation'], label='Log Transformation')
plt.legend(loc='best')
plt.title('Log Transformation')

plt.tight_layout()
plt.show()
```


## ORIGINAL DATA:

![image](https://github.com/user-attachments/assets/9cf0b048-4fb0-422c-921d-0e2846bc6a60)


## REGULAR DIFFERENCING:

![image](https://github.com/user-attachments/assets/d245ebcd-adb4-448c-95c7-ee2ebf71a3da)


## SEASONAL ADJUSTMENT:

![image](https://github.com/user-attachments/assets/a5906fb8-b23f-4b8d-8341-b226c287389f)


## LOG TRANSFORMATION:

![image](https://github.com/user-attachments/assets/5e9cc65f-793e-4b60-9b5f-732a91e5f1f5)

## RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger data.
