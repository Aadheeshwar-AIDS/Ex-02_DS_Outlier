# Ex-02_DS_Outlier
## AIM:
 
 ### To detect and remove the outliers from the given csv file.
 <br>
 
## ALGORITHM:

### Step 1 : Create a new file in jupyter notebook.
### Step 2 : Upload the given csv file.
### Step 3 : Open the csv file.
### Step 4 : Write codes for outliers detection and removal operation.
### Step 5 : Use quantile formulas and boxplot.
### Step 6 : End the program.
<br>

### CODE:
~~~
import pandas as pd
df = pd.read_csv("weight.csv")
df
df.drop('Gender',axis=1)
df
df.drop('Gender',axis=1,inplace=True)
df
df.boxplot()
from scipy import stats
import numpy as np
z = np.abs(stats.zscore(df))
z
df1 = df.copy()
df1 = df[(z<3).all(axis = 1)]
df1.boxplot()
df1
df2 = df.copy()
q1 = df2.quantile(0.25)
q3 = df2.quantile(0.75)
IQR = q3-q1
df2_new=df2[((df2>=q1-1.5*IQR)&(df2<=q3+1.5*IQR)).all(axis=1)]
df2_new.boxplot()
df2_new
~~~
<br>

## OUTPUT:
![output](Screenshot%20(205).png)
![output](Screenshot%20(206).png)
![output](Screenshot%20(207).png)
![output](Screenshot%20(208).png)
![output](Screenshot%20(209).png)

<br>

## RESULT:
Thus the Outliers are detected and removed from the Dataset.

