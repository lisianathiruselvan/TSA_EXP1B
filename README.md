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

![Screenshot 2025-03-18 132516](https://github.com/user-attachments/assets/8f9663ab-e8fa-40ba-9512-e88c76ba42bd)


REGULAR DIFFERENCING:
![Screenshot 2025-03-18 132532](https://github.com/user-attachments/assets/75a46617-a9db-498e-b786-48519365ba68)



SEASONAL ADJUSTMENT:

![Screenshot 2025-03-18 132516](https://github.com/user-attachments/assets/d1e26661-bc39-4039-a4ff-465d26cfad2c)




LOG TRANSFORMATION:

![Screenshot 2025-03-18 132516](https://github.com/user-attachments/assets/86ab14b7-8f70-4f60-999a-4e9cc50ee379)




### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
