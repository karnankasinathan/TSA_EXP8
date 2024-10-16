### Name : Karnan K
### Reg no : 212222230062
### Date: 
# Ex.No: 08     MOVINTG AVERAGE MODEL AND EXPONENTIAL SMOOTHING


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
# Step 1: Import necessary libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import warnings
# Step 2: Read the airline baggage complaints dataset from a CSV file
data = pd.read_csv('/content/baggagecomplaints.csv')  # Change to your actual file path
print("Shape of the dataset:", data.shape)
print(data.head(20))
# Step 3: Set figure size and suppress warnings
plt.figure(figsize=(12, 6))
warnings.filterwarnings("ignore")
# Step 4: Plot the first 50 values of the 'Complaints' column
plt.plot(data['Baggage'].head(50), marker='o')
plt.title('First 50 Values of Airline Baggage Complaints')
plt.xlabel('Time')
plt.ylabel('Complaints')
plt.grid()
plt.show()
# Step 5: Perform rolling average transformation with a window size of 5
rolling_mean_5 = data['Baggage'].rolling(window=5).mean()
print("First 10 values of rolling mean (window=5):", rolling_mean_5.head(10))
# Perform rolling average transformation with a window size of 10
rolling_mean_10 = data['Baggage'].rolling(window=10).mean()
print("First 10 values of rolling mean (window=10):", rolling_mean_10.head(10))
# Step 6: Create a new figure for plotting the original data and fitted values
plt.figure(figsize=(12, 6))
plt.plot(data['Baggage'], label='Original Data', color='blue')
plt.plot(rolling_mean_5, label='Rolling Mean (window=5)', color='red')
plt.plot(rolling_mean_10, label='Rolling Mean (window=10)', color='green')
plt.title('Original Data and Rolling Means')
plt.xlabel('Time')
plt.ylabel('Complaints')
plt.legend()
plt.grid()
plt.show()
# Step 7: Perform exponential smoothing
alpha = 0.2  # Smoothing factor
data['Exponential_Smoothing'] = data['Baggage'].ewm(alpha=alpha, adjust=False).mean()
# Plot the original data and exponential smoothing
plt.figure(figsize=(12, 6))
plt.plot(data['Baggage'], label='Original Data', color='blue')
plt.plot(data['Exponential_Smoothing'], label='Exponential Smoothing', color='orange')
plt.title('Original Data and Exponential Smoothing')
plt.xlabel('Time')
plt.ylabel('Complaints')
plt.legend()
plt.grid()
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-16 172839](https://github.com/user-attachments/assets/db3ac243-52e6-4c09-95c8-8134510a5df6)

Moving Average

![Screenshot 2024-10-16 172851](https://github.com/user-attachments/assets/6f741eea-4e0e-4926-9212-88f535fc04aa)


Exponential Smoothing

![Screenshot 2024-10-16 172858](https://github.com/user-attachments/assets/ed2a4b40-c12f-4f63-96e6-051e19e408a9)


### RESULT:
Thus the program successfully implemented the Moving Average Model and Exponential smoothing using python.
