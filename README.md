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


# CODE:
```
Developed by:LOGESHWARI.P
Register no:212221230055

import pandas as pd
import numpy as np
df=pd.read_csv("Superstore.csv")

df.head()

# Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

#1.Line plot

plt.figure(figsize=(8,5))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

#2.Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

#3.Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)

#4.Violin Plot

sns.violinplot(x="Profit",data=df)

#5.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

#6.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

#7.Count plot

sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df)

#8.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

#9.KDE Plot

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

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
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

# OUTPUT:
## Reading the given dataset:
![171085575-850daf1b-9595-42da-b02d-8c4c5d7c6aca](https://user-images.githubusercontent.com/94211349/171546287-b38b83df-3c66-48cb-9078-0ae23db3b800.png)
# Data Visualization Using Seaborn:
## 1.Lineplot:
![171085679-aae1afbe-1db7-4440-8491-d48f8ba90440](https://user-images.githubusercontent.com/94211349/171546420-5f0bab49-90ee-4c7a-ac11-dbd00d38cc07.png)
![171085711-2b03d8d7-8910-4982-b2fe-734faa6b8fc8](https://user-images.githubusercontent.com/94211349/171546503-5a914754-b2a0-4d14-9878-482a31e784b2.png)
## 2.Scatterplot:
![171085780-cedd0de2-e5b5-488a-988a-0659373a2d22](https://user-images.githubusercontent.com/94211349/171546583-bdece230-f906-4559-9911-99f81789939d.png)
![171085794-df911e71-8293-43a4-8ff0-f55b055af1db](https://user-images.githubusercontent.com/94211349/171546642-89f757a7-c142-41ae-b604-b097ad893edb.png)
## 3.Boxplot:
![171085856-61713565-712d-47e7-bf95-a84611b044f1](https://user-images.githubusercontent.com/94211349/171546726-988e1421-3677-4db7-a80c-897b8981e0f8.png)
![171085865-4f7001be-af02-4ae1-a961-cd02ea9b3d38](https://user-images.githubusercontent.com/94211349/171546765-38ba9723-bbd1-4f6d-97d8-902d52bd8e45.png)
## 4.Violinplot:
![171085903-b62abd5e-ed57-4cdf-ad1d-9adead1a339d](https://user-images.githubusercontent.com/94211349/171546818-ff51e730-090f-4099-bf52-a601be303073.png)
## 5.Barplot:
![171085953-dfd8ae08-2d07-433d-936f-62495220c1ed](https://user-images.githubusercontent.com/94211349/171546944-12c47565-3dfb-4a4c-8f82-c17f9795b7ac.png)
![171085962-1c1a755d-de30-443d-ae3b-f680304c118c](https://user-images.githubusercontent.com/94211349/171546972-2de5b40e-957d-46c8-a8ab-68108342c224.png)
## 6.Pointplot:
![171086011-0336e283-6007-4b98-8cfa-6d5b42c53e27](https://user-images.githubusercontent.com/94211349/171547040-5203fe15-fb45-4e56-a70f-12e0e3c84942.png)
## 7.Countplot:
![171086056-1973e990-37f1-44e4-b5fe-1813db8f8305](https://user-images.githubusercontent.com/94211349/171547132-df0d2eba-4a50-4b88-8da4-788ad1b78e20.png)
## 8.Histogram:
![171086086-5424206f-e653-4ee7-874f-8f72e1273fed](https://user-images.githubusercontent.com/94211349/171547238-c5e1262b-ac31-4200-b0b4-f1dc99c1bc33.png)
## 9.KDE Plot:
![171086130-79c27dc8-1e52-483c-821a-e505bcbdfc39](https://user-images.githubusercontent.com/94211349/171547325-eef59f98-473c-4d15-8b42-21b18232494f.png)
# Data Visualization Using Matplotlib:
## 1.Plot:
![171086746-edc3d53b-febc-4f31-bdac-ffe0ca1eb0f5](https://user-images.githubusercontent.com/94211349/171547544-cf06fdc9-936f-4d52-ae32-cd0299f43e88.png)
## 2.Heat map:
![171086842-9955d932-2dac-4ba1-8cb9-92783d01af0d](https://user-images.githubusercontent.com/94211349/171547593-48a7db96-5a38-4fce-b421-ca9555938c35.png)
![171086855-960093de-e62d-4c1f-a3e3-58902f55d413](https://user-images.githubusercontent.com/94211349/171547637-4414b801-912c-4905-b76e-1f36b7d1af26.png)
## 3.PieChart:
![171086879-8bb2bdde-a899-4515-8397-26fccb28f2d6](https://user-images.githubusercontent.com/94211349/171547712-ec888ff2-5f8e-4a76-956a-68947ba7b160.png)
![171086913-7a9f4736-6d76-4c65-8aef-55c8de0a3ce6](https://user-images.githubusercontent.com/94211349/171547738-17c035d6-f308-44f3-abf2-ac740d5ec712.png)
## 4.Histogram:
![171086927-4fc2a1d5-34a7-41fc-8318-b78810b0b915](https://user-images.githubusercontent.com/94211349/171547875-7979e83b-ebc4-4ca9-a90f-a02820b4a630.png)
## 5.Bargraph:
![171086940-b16b362f-0157-48d5-b3f7-08735b0e2ad8](https://user-images.githubusercontent.com/94211349/171547978-3f3b4604-3715-4f15-8de5-50cf3b05ea6f.png)
## 6.Scatterplot:
![171087086-ce5fba1d-1856-4e0f-8a20-ffada0ac66d3](https://user-images.githubusercontent.com/94211349/171548010-dc705d7c-ea92-441b-992c-c4e43fde2156.png)
## 7.Boxplot:
![171087099-a24f0cb6-1c49-479a-bd15-adac86d7198b](https://user-images.githubusercontent.com/94211349/171548073-1944894b-80bb-4117-a2ab-728054203fe1.png)

# RESULT:
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.



