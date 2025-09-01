# TSA-3
# COMPUTE-THE-AUTO-FUNCTION-ACF

### Name : Mohamed Nadheem N
### Date: 01.09.2025

### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.

   
### PROGRAM:
```
import matplotlib.pyplot as plt
import numpy as np

# Given data
data = [3, 16, 156, 47, 246, 176, 233, 140, 130, 101, 166, 201, 200, 116, 118, 
        247, 209, 52, 153, 232, 128, 27, 192, 168, 208, 187, 228, 86, 30, 151, 
        18, 254, 76, 112, 67, 244, 179, 150, 89, 49, 83, 147, 90, 33, 6, 158, 
        80, 35, 186, 127]

lags = range(35)

# Convert to numpy array
data = np.array(data)
N = len(data)

# Mean and variance
mean = np.mean(data)
var = np.var(data)

# Normalize data
normalized = data - mean

# Pre-allocate autocorrelation values
acf_values = []

# Compute autocorrelation for each lag
for lag in lags:
    num = np.sum(normalized[:N-lag] * normalized[lag:])
    den = (N - lag) * var
    acf = num / den
    acf_values.append(acf)

# Display the ACF graph
plt.figure(figsize=(10,5))
plt.stem(lags, acf_values, basefmt=" ")
plt.xlabel("Lags")
plt.ylabel("ACF")
plt.title("AutoCorrelation Function (First 35 Lags)")
plt.grid(True)
plt.show()

print("ACF values for first 35 lags:")
print(acf_values)

```

### OUTPUT:
<img width="1463" height="786" alt="Screenshot 2025-09-01 152328" src="https://github.com/user-attachments/assets/7057b66a-cd35-4514-b53b-d02a4f9251c1" />

### RESULT:
        Thus we have successfully implemented the auto correlation function in python.
