# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("titanic_dataset.csv")
dt
```
<img width="1185" height="944" alt="image" src="https://github.com/user-attachments/assets/125e8fac-19e0-42bc-b9d1-c7a61bf08e99" />

```
dt.info()
dt.shape
dt.set_index("PassengerId",inplace=True)
dt
```
<img width="1226" height="1277" alt="image" src="https://github.com/user-attachments/assets/50baedea-d058-4089-b7d2-50a93fbae8e0" />
<img width="1188" height="415" alt="image" src="https://github.com/user-attachments/assets/598063b8-c959-47fc-97d0-e54c7179056c" />

```
dt.nunique()
```
<img width="1177" height="323" alt="image" src="https://github.com/user-attachments/assets/dc50ab71-51cb-48fe-9eae-98f6d99ef905" />

```

dt["Survived"].value_counts()
sns.countplot(x="Survived",data=dt)
dt.Survived.unique()
```

<img width="1207" height="928" alt="image" src="https://github.com/user-attachments/assets/46273ca0-9ee2-478a-954a-9b5c5848bab1" />

```

dt.rename(columns = {'Sex':'Gender'}, inplace = True)
dt

```

<img width="1179" height="785" alt="image" src="https://github.com/user-attachments/assets/2da23867-60bd-4f1e-b947-38433ad6bc2b" />

```

sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
dt.boxplot(column="Age",by="Survived")

```

<img width="1196" height="1409" alt="image" src="https://github.com/user-attachments/assets/67cbed31-2a0b-4cae-a3db-ba4f87974971" />

<img width="1178" height="719" alt="image" src="https://github.com/user-attachments/assets/a72ded99-fb0e-49f0-ad7e-781752df24d6" />

```

fig,ax1=plt.subplots(figsize=(8,5))

plt = sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)

```

<img width="1206" height="714" alt="image" src="https://github.com/user-attachments/assets/053a60df-c260-4e53-b5fb-6308a736f5e7" />

```

sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")

```

<img width="1183" height="637" alt="image" src="https://github.com/user-attachments/assets/13bc3522-c6d4-4cec-a6b3-f5c2eec418e6" />

```

numeric_dt = dt.select_dtypes(include=np.number)
corr = numeric_dt.corr()
sns.heatmap(corr,annot = True)

```

<img width="1184" height="694" alt="image" src="https://github.com/user-attachments/assets/6a3ff984-5947-4397-8cf5-7abb1c6d3bc6" />

```

sns.pairplot(dt)

```

<img width="1186" height="1179" alt="image" src="https://github.com/user-attachments/assets/5be876e4-1668-4ee0-b1b0-fb35465ebda6" />

# RESULT
Thus we have successfully performed Exploratory Data Analysis on the given data set.
