# Ex.No: 08     MOVINTG AVERAGE MODEL AND EXPONENTIAL SMOOTHING
### Date: 


### AIM:
To implement Moving Average Model and Exponential smoothing Using Python.
### ALGORITHM:
1. Import necessary libraries
2. Read the electricity time series data from a CSV file,Display the shape and the first 20 rows of
the dataset
3. Set the figure size for plots
4. Suppress warnings
5. Plot the first 50 values of the 'Value' column
6. Perform rolling average transformation with a window size of 5
7. Display the first 10 values of the rolling mean
8. Perform rolling average transformation with a window size of 10
9. Create a new figure for plotting,Plot the original data and fitted value
10. Show the plot
11. Also perform exponential smoothing and plot the graph
### PROGRAM:
```
# Import necessary libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import warnings
warnings.filterwarnings('ignore')

# Read the Gold dataset from a CSV file
data = pd.read_csv('Gold Price Prediction.csv')  # Replace with the correct file path

# Display the shape and the first 20 rows of the dataset
print("Shape of the dataset:", data.shape)
print("First 20 rows of the dataset:")
print(data.head(20))

# Set the figure size for plots
plt.rcParams['figure.figsize'] = [10, 6]

# Plot the first 50 values of the 'Price Today' column
plt.plot(data['Price Today'][:50])
plt.title('First 50 Values of "Price Today"')
plt.xlabel('Index')
plt.ylabel('Price Today')
plt.grid(True)
plt.show()

# Perform rolling average transformation with a window size of 5 on 'Price Today'
rolling_mean_5 = data['Price Today'].rolling(window=5).mean()

# Display the first 10 values of the rolling mean
print("First 10 values of the rolling mean (window size 5):")
print(rolling_mean_5.head(10))

# Perform rolling average transformation with a window size of 10 on 'Price Today'
rolling_mean_10 = data['Price Today'].rolling(window=10).mean()

# Create a new figure for plotting
plt.figure()

# Plot the original data and fitted value (rolling mean with window size 10)
plt.plot(data['Price Today'], label='Original Data')
plt.plot(rolling_mean_10, label='Rolling Mean (window=10)', color='orange')
plt.title('Original Data and Rolling Mean (window=10)')
plt.xlabel('Index')
plt.ylabel('Price Today')
plt.legend()
plt.grid(True)
plt.show()

# Perform exponential smoothing on 'Price Today' and plot the graph
alpha = 0.3  # Smoothing factor
exp_smooth = data['Price Today'].ewm(alpha=alpha).mean()

plt.figure()
plt.plot(data['Price Today'], label='Original Data')
plt.plot(exp_smooth, label='Exponential Smoothing', color='red')
plt.title('Original Data and Exponential Smoothing')
plt.xlabel('Index')
plt.ylabel('Price Today')
plt.legend()
plt.grid(True)
plt.show()
```
### OUTPUT:
## data:
![image](https://github.com/user-attachments/assets/1e9d36d8-987c-4845-a3f4-4144e50fef21)

## Price Today
![image](https://github.com/user-attachments/assets/f9a5b49e-e8e6-4e45-9d98-606c19ec00a6)

## Original Data and Rolling Mean
![image](https://github.com/user-attachments/assets/82954833-9966-4860-945f-995f94a50d46)
## Exponential Smoothing

![image](https://github.com/user-attachments/assets/1e430e29-f05a-402d-8ec6-89f1fe2901a6)


### RESULT:
Thus we have successfully implemented the Moving Average Model and Exponential smoothing using python.
