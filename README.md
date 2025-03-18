# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 

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

data=pd.read_csv("/content/yahoo_stock.csv")

#original data
x=data['Date']
y=data['Open']
plt.xlabel('Date')
plt.ylabel('Open')
plt.plot(x,y)

#regular differencing
 data3=data
 data3['diff']=data3['Date']
 data3=data3.dropna()
 x=data3['Open']
 y=data3['diff']
 plt.xlabel('Open')
 plt.ylabel('Date')
 plt.plot(y,x)

#seasonal adjustment
data1=data
data1['SeasonalAdjustment'] = data1['Open'].rolling(window=12).mean()
data1['SeasonalAdjustment'].dropna()
x=data1['Date']
y=data1["SeasonalAdjustment"]
plt.xlabel('Date')
plt.ylabel('Volume')
plt.plot(x,y)

#log transformation
data2=data
data1['log'] = np.log(data1['Close'].dropna())
y=data1['Date']
x=data2["log"]
plt.xlabel('Date')
plt.ylabel('Close')
plt.plot(y,x)
```

### OUTPUT:


REGULAR DIFFERENCING:
![image](https://github.com/user-attachments/assets/ecb4311e-c05a-442d-88d6-dcbe5e651e13)



SEASONAL ADJUSTMENT:
![image](https://github.com/user-attachments/assets/0665b09f-c83b-42a4-b7e3-7349faee21d1)



LOG TRANSFORMATION:
![image](https://github.com/user-attachments/assets/85c9a6fa-e266-4d17-a2e9-10ecda959e62)




### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on yahoo stocks data.
