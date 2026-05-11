# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 11.05.2026


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
# Step 1: Load the dataset, Convert 'Date' column to datetime format, Set it as index
data = pd.read_csv(r"./FINAL_USO.csv", parse_dates=["Date"], index_col="Date")
# Step 2: Perform seasonal decomposition using the correct column name
decomposition = seasonal_decompose(data["Close"], model="additive", period=252)
# Step 3: Plot the decomposition
plt.figure(figsize=(10, 12))  # Adjust the figure size for a square shape
# decomposition.plot() this plots all four of the following graphs
# Original Data
plt.subplot(411)
plt.plot(data["Close"], label="Daily Gold Price (USO Close)")
plt.legend(loc="upper left")
plt.title("Daily Gold Price (USO Close)")
# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label="Trend", color="orange")
plt.legend(loc="upper left")
plt.title("Linear Trend Plot")
# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label="Seasonal", color="green")
plt.legend(loc="upper left")
plt.title("Seasonality Plot")
# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label="Residual", color="red")
plt.legend(loc="upper left")
plt.title("Residual Plot")
plt.tight_layout()
plt.show()
```

### OUTPUT:
<img width="990" height="1189" alt="image" src="https://github.com/user-attachments/assets/bb70be30-0e54-4ee0-8466-ac88d7c35bc1" />

### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
