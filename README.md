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
NAME:LISIANA T
REG NO:212222240053
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

data=pd.read_csv('/content/World Population.csv')

x=data['Rank']
y=data['Percentage']
plt.xlabel('Rank')
plt.ylabel('Percentage')
plt.plot(x,y)


data1=data
data1['SeasonalAdjustment'] = data1['Percentage'].diff(periods=12)
data1['SeasonalAdjustment'].dropna()
x=data1['Rank']
y=data1["SeasonalAdjustment"]
plt.xlabel('Rank')
plt.ylabel('Percentage')
plt.plot(x,y)

data3=data
data3['diff']=data3['Percentage'].diff()
data3=data3.dropna()
x=data3['Rank']
y=data3['diff']
plt.xlabel('Rank')
plt.ylabel('Percentage')
plt.plot(x,y)


data2=data
data2['log']=np.log(data2['diff']).dropna()
data2=data2.dropna()
x=data2['Rank']
y=data2['log']
plt.xlabel('Rank')
plt.ylabel('Percentage')
plt.plot(x,y)
### OUTPUT:
PLOT WITHOUT CONVERSION:

![image](https://github.com/user-attachments/assets/eecf7034-1df4-48e5-83ac-bb423a40a417)


REGULAR DIFFERENCING:
![image](https://github.com/user-attachments/assets/0da6cc35-661f-4d9c-b777-aba95e3641fa)


SEASONAL ADJUSTMENT:

![image](https://github.com/user-attachments/assets/aabebc82-b449-4bb0-9529-75718ad9e7ae)



LOG TRANSFORMATION:

![image](https://github.com/user-attachments/assets/f31a09cb-a3f1-4adf-9133-7c6a6e985181)




### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
