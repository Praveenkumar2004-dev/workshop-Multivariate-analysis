# workshop-Multivariate-analysis

## AIM:
To Perform Bivariate/Multivariate Analysis

## ALGORITHM:
## STEP1
Import the built libraries required to perform EDA and outlier removal.

## STEP2
Read the given csv file.

## STEP3
Convert the file into a dataframe and get information of the data.

## STEP4
Return the objects containing counts of unique values using (value_counts()).

## STEP5
Plot the counts in the form of Histogram or Bar Graph.

## STEP6
Use seaborn the bar graph comparison of data can be viewed.

## STEP7
Find the pairwise correlation of all columns in the dataframe.corr()

## STEP8
Save the final data set into the file.

## TYPES OF BIVARIATE ANALYSIS
```
1)Numerical & Numerical(Scatter plot)
2)Numerical & Categorical(Bar plot,Box plot,Dist plot)
```

## PROGRAM:
NAME:S.PRAVEEN KUMAR

REG.NO:212222230108
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df = pd.read_csv("FlightInformation.csv")
df
df.head()
df.info()
df.isnull().sum()
df['Route'] = df['Route'].fillna(df['Route'].mode()[0])
df['Total_Stops'] = df['Total_Stops'].fillna(df['Total_Stops'].mode()[0])
df.isnull().sum()
df.shape
plt.figure(figsize=(8,5))
plt.xticks(rotation = 80)
sns.barplot(df["Airline"],df["Price"],hue=df["Total_Stops"])
states=df.loc[:,["Source","Price"]]
states=states.groupby(by=["Source"]).sum().sort_values(by="Price")
plt.figure(figsize=(8,7))
sns.barplot(x=states.index,y="Price",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SOURCE")
plt.ylabel=("PRICE")
plt.show()
plt.figure(figsize=(5,7))
sns.scatterplot(df['Source'], df['Price'], hue=df['Destination'])
plt.xticks(rotation = 90)
df_count = df.groupby(by=["Source"]).count()
labels=[]
for i in df_count.index:
    labels.append(i)
plt.figure(figsize=(8,8))
colors = sns.color_palette("Set2")
plt.pie(df_count["Price"], colors = colors, labels=labels, autopct = "%0.0f%%",shadow = True) 
plt.title("Source")
plt.show()
df['Airline'].value_counts()
df['Duration'].value_counts()
df_segment = df.groupby(by=["Total_Stops"]).count()
labels = []
for i in df_segment.index:
    labels.append(i)

plt.figure(figsize=(6,6))
colors = sns.color_palette('pastel')
pie = plt.pie(df_segment["Price"], colors = colors, autopct = "%0.0f%%",shadow = True)
plt.title("Total Stops")
plt.legend(pie[0], labels, loc="upper right")
plt.show()
df_region = df.groupby(by=["Destination"]).count()
labels = []
for i in df_region.index:
    labels.append(i)
    
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
pie = plt.pie(df_region["Price"], colors = colors, autopct = "%0.0f%%",shadow = True)
plt.title("Destination")
plt.legend(pie[0], labels, loc="upper right")
plt.show()
```

## OUTPUT:

![1](https://user-images.githubusercontent.com/119559827/229036243-b2a94010-5c98-4135-8371-d8f5b10889c9.png)
![2](https://user-images.githubusercontent.com/119559827/229036280-5bb5bcaf-09ec-4ab6-8de3-2abf499a3923.png)
![3](https://user-images.githubusercontent.com/119559827/229036301-bdf17779-ec01-4a04-b79a-b853b3dea310.png)
![4](https://user-images.githubusercontent.com/119559827/229036434-fb36daf9-09b7-49f4-a1ab-487a07384b19.png)
![5](https://user-images.githubusercontent.com/119559827/229036470-d99fbc2d-8e76-4ed9-be99-81387527dcf7.png)
![6](https://user-images.githubusercontent.com/119559827/229036529-f8502566-320e-494b-90e5-a21fa5877038.png)
![7](https://user-images.githubusercontent.com/119559827/229036561-d886a292-2845-413e-83d3-692c825e5018.png)
![8](https://user-images.githubusercontent.com/119559827/229036587-fedd36ee-6301-4422-a3ca-acb2f60fd0d5.png)
![9](https://user-images.githubusercontent.com/119559827/229036606-a5621335-6c4b-4730-9ed9-ab51b0797f06.png)
![10](https://user-images.githubusercontent.com/119559827/229036621-cc924be2-94d7-4f7f-977a-19a6b7a80cef.png)
![11](https://user-images.githubusercontent.com/119559827/229036667-9e87bed7-20a7-4a19-b735-4bc1943689da.png)
![12](https://user-images.githubusercontent.com/119559827/229036701-04d925b6-e78b-4f9b-9b50-84ece177140b.png)

## RESULT:
Thus we applied Bivariate/Multivariate Analysis Successfully

