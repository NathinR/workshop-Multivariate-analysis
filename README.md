# workshop-Multivariate-analysis
# AIM:
To perform multivarient analysis on the given data set.

# ALGORITHM:
1.Clean the data

2.Remove outliers

3.Apply the skew function and Kurtosis

4.Apply Bivariate analysis on numerical and categorical

5.Apply Multivariate analysis.

# CODE:
BIVARIATE ANALYSIS:
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_excel("/content/FlightInformation.xlsx")
df.info()
df.isnull().sum()
df['Route']=df['Route'].fillna(df['Route'].mode()[0])
df['Total_Stops']=df['Total_Stops'].fillna(df['Total_Stops'].mode()[0])
df.isnull().sum()
sns.scatterplot(x="Duration",y="Price",data=df)
sns.scatterplot(x="Airline",y="Price",data=df)
plt.figure(figsize=(115,15))
sns.boxplot(x="Source",y="Price",data=df)
sns.displot(df,x="Source",hue="Destination")
sns.barplot(x=df['Price'],y=df['Source'],data=df)
```

MULTIVARIATE ANALYSIS:
```
pa=pa.groupby(by=["Duration"]).sum().sort_values(by="Price")
plt.figure(figsize=(75,20))
sns.barplot(x=pa.index,y="Price",data=pa)
plt.xticks(rotation = 90)
plt.xlabel=("Duration")
plt.ylabel=("Price")
plt.show()
bas=df.loc[:,["Airline","Price"]]
bas=bas.groupby(by=["Airline"]).max().sort_values(by="Price")
plt.figure(figsize=(17,7))
sns.barplot(x=bas.index,y="Price",data=bas)
plt.xticks(rotation = 90)
plt.xlabel=("AIRLINE")
plt.ylabel=("PRICE")
plt.show()
c=df.loc[:,["Airline","Price"]]
c=c.groupby(by=["Airline"]).min().sort_values(by="Price")
plt.figure(figsize=(17,7))
sns.barplot(x=c.index,y="Price",data=c)
plt.xticks(rotation = 90)
plt.xlabel=("AIRLINE")
plt.ylabel=("PRICE")
plt.show() 
```

# OUTPUT:

### Bivariate

![image](https://user-images.githubusercontent.com/118679646/230829692-b35013d9-bdae-44df-8726-1274d16d045d.png)
![image](https://user-images.githubusercontent.com/118679646/230829749-84d75ee4-6dd1-4a75-958b-d93d5c175f83.png)
![image](https://user-images.githubusercontent.com/118679646/230829922-881590db-2725-4134-961a-49de145588fe.png)
![image](https://user-images.githubusercontent.com/118679646/230830002-711b302d-37ca-4d7b-acc3-684725f5407f.png)

### Multivariate:
MEAN
![image](https://user-images.githubusercontent.com/118679646/230830434-6093deed-9950-4c2b-94cc-ca9d1e0b6d2e.png)

MAX
![image](https://user-images.githubusercontent.com/118679646/230830548-a17f8d5b-4dc9-42a2-9a0f-a508fd6f21b8.png)

SUM
![image](https://user-images.githubusercontent.com/118679646/230830642-9cf1df95-c77e-46c6-82ff-82dbff5a6ce0.png)

MIN
![image](https://user-images.githubusercontent.com/118679646/230830745-da6892c4-9816-49a9-9383-c964b4348245.png)

Heat Map

![image](https://user-images.githubusercontent.com/118679646/230830834-5f0c361a-6e2f-4af4-91f4-20adf5e1d882.png)


