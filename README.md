# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE
```
# Importing packages
import pandas as pd
import numpy as np
import seaborn as sns
from matplotlib import pyplot as plt
# Reading dataset
df=pd.read_csv("Superstore.csv",encoding=('ISO-8859-1'))
df.head() 
#Data Visualization using Seaborn
#1.Line plot
plt.figure(figsize=(8,5))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
#2.Scatterplot
sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)
#3.Boxplot
sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)
#4.Barplot
sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)
#5.Pointplot
sns.pointplot(x=df["Quantity"],y=df["Discount"])
#6.Count plot
sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df) 
#7.Histogram
sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')
#8.KDE Plot
sns.kdeplot(x="Profit", data = df,hue='Category')
#Data Visualization Using MatPlotlib
#1.Plot
plt.plot(df['Category'], df['Sales'])
plt.show()
#2.Heatmap
df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)
#3.Piechart
df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()
#4.Histogram
plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()
#5.Bargraph
plt.bar(df.index,df['Category'])
plt.show()
#6.Scatterplot
plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()
#7.Boxplot
plt.boxplot(x="Sales",data=df)
plt.show()
```

# OUPUT
![image](https://user-images.githubusercontent.com/98682825/174454953-380365bb-bdce-474b-a30d-b0f39fea1c2a.png)
![image](https://user-images.githubusercontent.com/98682825/174454960-3f20f23a-ac5e-4e34-8fd9-e44a33345495.png)
![image](https://user-images.githubusercontent.com/98682825/174454969-c905098e-047e-472f-af17-6441bf8066c4.png)

## Scatterplot
![image](https://user-images.githubusercontent.com/98682825/174454992-9f28afc6-e967-4b50-a320-90edf70e0aa2.png)
![image](https://user-images.githubusercontent.com/98682825/174455042-b7e41afb-a607-411b-bdcd-681ddd4290b1.png)
![image](https://user-images.githubusercontent.com/98682825/174455056-daae0c2b-6008-4297-bd6e-12b96ff7e6b8.png)

## Boxplot
![image](https://user-images.githubusercontent.com/98682825/174455067-254da654-9725-4ee0-adce-16a408de0bb7.png)
![image](https://user-images.githubusercontent.com/98682825/174455103-67eef030-fa5c-4693-94ea-d0e596e42b59.png)

## Barplot
![image](https://user-images.githubusercontent.com/98682825/174455133-4b7cf430-8b9b-4162-b2de-335874698f26.png)
![image](https://user-images.githubusercontent.com/98682825/174455142-ed52bf27-97be-401e-8248-2483ad0b227a.png)
![image](https://user-images.githubusercontent.com/98682825/174455150-6e0c5d0b-4aae-4cf5-b472-1cb2a9a8aa10.png)

## Pointplot
![image](https://user-images.githubusercontent.com/98682825/174455167-4cd12145-0b0d-41b6-a083-117ef7c0557b.png)

## Countplot
![image](https://user-images.githubusercontent.com/98682825/174455181-9ecdb69c-1d91-477c-b491-27757aa092a2.png)
![image](https://user-images.githubusercontent.com/98682825/174455187-cdc7d23c-a83f-4016-86b9-bdd8546877cd.png)

## Histogram
![image](https://user-images.githubusercontent.com/98682825/174455198-5e2ecbdb-7bdc-46cc-b0c5-28720793fc5d.png)

## KDE Plot
![image](https://user-images.githubusercontent.com/98682825/174455217-a1ff2853-9bc4-47c7-af11-5d9c0d6a33b8.png)

# Data Visualization Using MatPlotlib

## Plot
![image](https://user-images.githubusercontent.com/98682825/174455252-e2bfd3c9-7e0d-48eb-9863-7b56c5b1c16a.png)

## Heatmap
![image](https://user-images.githubusercontent.com/98682825/174455270-9e2cebaa-b3ae-4a9b-8569-14562337d380.png)

## Piechart
![image](https://user-images.githubusercontent.com/98682825/174455279-0a81733b-a5aa-49dc-8dde-6d863b20d39c.png)

## Histogram
![image](https://user-images.githubusercontent.com/98682825/174455289-c5f0e54b-8cd8-412e-a9e0-898953ece07a.png)

## Bargraph
![image](https://user-images.githubusercontent.com/98682825/174455301-301e78ec-3c66-445c-a938-23abe75a7917.png)

## Scatterplot
![image](https://user-images.githubusercontent.com/98682825/174455332-0977c918-f58b-4ca3-9b4f-03c80870bee6.png)

## Boxplot
![image](https://user-images.githubusercontent.com/98682825/174455345-1534915b-fffe-4d3b-921b-c68bfeca0d54.png)

## RESULT
    Hence, Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.







