# Ex-02_DS_Outlier
## AIM:
To detect and remove the outliers from the given csv file.
## ALGORITHM:
### STEP 1:
Create a new file in jupyter notebook.
### STEP 2:
Upload the given csv file.
### STEP 3:
Open the csv file.
### STEP 4:
Write codes for outliers detection and removal operation.
### STEP 5:
Use quantile formulas and boxplot.
### STEP 6:
End the program.
## CODE:
```
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
```
## OUTPUT:
![Screenshot (205)](https://user-images.githubusercontent.com/93427278/161588987-17021626-60d2-4f1c-82eb-1012c8538c82.png)
![Screenshot (206)](https://user-images.githubusercontent.com/93427278/161589041-ee67cf70-d0ef-493c-b0fc-578e038fc779.png)
![Screenshot (207)](https://user-images.githubusercontent.com/93427278/161589092-b4d3c709-2bcc-4af8-b318-17d788ade6d5.png)
![Screenshot (208)](https://user-images.githubusercontent.com/93427278/161589147-778c36e2-b1db-47d2-a7ad-27a0b79c90b3.png)
![Screenshot (209)](https://user-images.githubusercontent.com/93427278/161589200-855ce997-6d5d-4ec5-8f70-902a3b185833.png)

## RESULT:
Thus the Outliers are detected and removed from the Dataset.
