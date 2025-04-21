# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```
Developed by: S KANUSHA SREE
REGISTER NUMBER: 212224040149
```
```
import seaborn as sns
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
x=[1,2,3,4,5]
y=[3,6,2,7,9]
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/9a7bc2bb-dd36-40e9-b2d7-5e920390e92b)
```
df=sns.load_dataset("tips")
df
```
![image](https://github.com/user-attachments/assets/d434530d-be7d-4456-9bc6-76cf2d7fcb4b)
```
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle="solid",legend="auto")
```
![image](https://github.com/user-attachments/assets/991be273-3d31-44ff-8262-362f3a443658)
```
x=[1,2,3,4,5]
y1=[3,5,6,3,1]
y2=[7,5,9,3,6]
y3=[5,3,7,1,4]
sns.lineplot(x=x,y=y1)
sns.lineplot(x=x,y=y2)
sns.lineplot(x=x,y=y3)
plt.title("MULTI-LINE PLOT")
plt.xlabel("X AXIS")
plt.ylabel("Y AXIS")
```
![image](https://github.com/user-attachments/assets/cd4a23f1-5b30-4624-acfd-a13a3ae498df)
```
avg_total_bill=df.groupby('day')['total_bill'].mean()
avg_tip=df.groupby('day')['tip'].mean()
print(avg_total_bill)
```
![image](https://github.com/user-attachments/assets/5aedcbdb-e5ac-44f1-ad10-a6573b2d0907)
```
print(avg_tip)
```
![image](https://github.com/user-attachments/assets/0c9761f3-5f51-4143-b298-812720893cac)
```
plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index,avg_total_bill,label="TOTAL BILL")
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="TIP")
plt.xlabel("Day of the week")
plt.ylabel('Amount')
plt.title("Average Total Bill and Tip by Day")
plt.legend()
```
![image](https://github.com/user-attachments/assets/93e668f1-7777-4549-b281-a6afbff7476f)
```
avg_total_bill=df.groupby('time')['total_bill'].mean()
avg_tip=df.groupby('time')['tip'].mean()
p1=plt.bar(avg_total_bill.index,avg_total_bill,label="TOTAL BILL",width=0.4)
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="TIP",width=0.4)
plt.xlabel("Time of Day")
plt.ylabel('Amount')
plt.title("Average Total Bill and Tip by Time of the Day")
plt.legend()
```
![image](https://github.com/user-attachments/assets/b471d3a8-2a29-43c7-b52c-578caf193744)
```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges= [8.962, 0.941, 8.938, 8.923, 0.918, 0.906, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896]
plt. bar(years,apples)
plt.bar(years,oranges,bottom=apples)
```
![image](https://github.com/user-attachments/assets/0444ad41-73e8-4cf9-b246-d15d735a82b8)
```
sns.barplot(x="day",y="total_bill",hue="sex",data=df,palette="Set1")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Total Bill")
```
![image](https://github.com/user-attachments/assets/97db35af-b9dc-404b-ac04-1d11eed70740)
```
tit=pd.read_csv("/content/titanic_dataset (2).csv")
tit
```
![image](https://github.com/user-attachments/assets/15566ef4-cbe6-44b9-9802-2e3a26520d08)
```
plt.figure(figsize=(8,5))
sns.barplot(x="Embarked",y='Fare',data=tit,palette='rainbow')
plt.title("Fare of passenger by Embarked town")
```
![image](https://github.com/user-attachments/assets/e140ac4a-7430-44b0-9a3f-2de61a897a00)
```
plt.figure(figsize=(8,5))
sns.barplot(x="Embarked",y='Fare',data=tit,palette='rainbow',hue='Pclass')
plt.title("Fare of passenger by Embarked town divided by class")
```
![image](https://github.com/user-attachments/assets/938c4b3c-29e6-4a8c-83d5-ef2f2170de70)
```
sns.scatterplot(x="total_bill",y='tip',hue="sex",data=df)
plt.xlabel("total bill")
plt.ylabel("tip amount")
plt.title("Scatter plot")
```
![image](https://github.com/user-attachments/assets/71e09b29-162f-454b-8e1f-5ceec989b3f8)
```
np.random.seed(1)
num=np.random.randn(1000)
num=pd.Series(num,name="Numerical Variable")
num
```
![image](https://github.com/user-attachments/assets/647158ff-902b-472c-9fa3-8e915909d0a7)
```
sns.histplot(data=num,kde=True)
```
![image](https://github.com/user-attachments/assets/a1535517-6f32-49d2-9f01-cf7371a1959f)
```
sns.histplot(data=tit,x="Pclass",hue='Survived',kde=True)
```
![image](https://github.com/user-attachments/assets/07a4ff7b-d1c8-4dfc-ba01-8cbe3980b5b8)
```
np.random.seed(0)
marks=np.random.normal(loc=70,scale=10,size=100)
marks
```
![image](https://github.com/user-attachments/assets/b947b439-d286-4a0f-a063-1aa21c03e7b3)
```
sns.histplot(data=marks,bins=10,kde=True,stat='count',cumulative=False,multiple='stack',element='bars',palette='Set1',shrink=0.7)
plt.xlabel("marks")
plt.ylabel("density")
plt.title("histogram")
```
![image](https://github.com/user-attachments/assets/ef5c106d-40d0-4a68-88d3-5d2301b70737)
```
sns.boxplot(x=df['day'],y=df['total_bill'],hue=df['sex'])
```
![image](https://github.com/user-attachments/assets/47bed018-2e9d-43ae-b862-edc124d6c1f2)
```
sns.boxplot(x='day',y='total_bill',hue='smoker',data=df,linewidth=2,width=0.6,boxprops={"facecolor":"lightblue","edgecolor":"darkblue"},whiskerprops={"color":"black","linestyle":"--","linewidth":1.5},capprops={"color":"black","linestyle":"--","linewidth":1.5})
```
![image](https://github.com/user-attachments/assets/02c8cea7-df16-4990-bdff-2c58afdbf4a8)
```
sns.boxplot(x='Pclass',y='Age',data=tit,palette='rainbow')
plt.title("age by passenger class,titanic")
```
![image](https://github.com/user-attachments/assets/28b68576-0bc0-4035-8e27-357e41c4fbed)
```
sns.violinplot(x='day',y='total_bill',hue='smoker',data=df,linewidth=2,width=0.6,palette="Set3",inner="quartile")
plt.xlabel("day of the week")
plt.ylabel("total bill")
plt.title("violin plot")
```
![image](https://github.com/user-attachments/assets/625c69b8-2ec1-4645-a016-5ac9e03a253e)
```
sns.violinplot(x='day',y='tip',data=df)
```
![image](https://github.com/user-attachments/assets/70d477dc-08f9-4434-bfab-7ae69d24400e)
```
sns.violinplot(x=df["total_bill"])
```
![image](https://github.com/user-attachments/assets/ad9a507d-d02e-426f-a914-45c8ffccb388)
```
sns.set(style="whitegrid")
sns.violinplot(x="tip",y="day",data=df)
```
![image](https://github.com/user-attachments/assets/74424b72-96b1-42a7-a5b3-30ab21c417a1)
```
sns.kdeplot(data=df,x="total_bill",hue="time",multiple="fill",linewidth=3,palette="Set2",alpha=0.8)
```
![image](https://github.com/user-attachments/assets/6a947752-dcfc-40db-a33d-45026a823551)
```
sns.kdeplot(data=df,x="total_bill",hue="time",multiple="layer",linewidth=3,palette="Set2",alpha=0.8)
```
![image](https://github.com/user-attachments/assets/5f68a045-18b2-457d-a2bf-9a4d7d3a42d6)
```
sns.kdeplot(data=df,x="total_bill",hue="time",multiple="stack",linewidth=3,palette="Set2",alpha=0.8)
```
![image](https://github.com/user-attachments/assets/443ae645-dce4-4533-bfb6-6b63feac5c85)
```
mart=pd.read_csv("")
mart
```
```
mart=mart[['Gender','Payment','Unit price','Quantity','Total','gross income']]
mart.head()
```
```
sns.kdeplot(data=mart,x='Total')
```
```
sns.kdeplot(data=mart,x='Unit price')
```
```
sns.kdeplot(data=mart)
```
```
sns.kdeplot(data=mart,x='Total',hue='Payment',multiple='stack')
```
```
sns.kdeplot(data=mart,x='Total',hue='Payment',multiple='stack',linewidth=5,palette='Dark2',alpha=0.5)
```
```
sns.kdeplot(data=mart,x='Unit price',y='gross income')
```
```
data=np.random.randint(low=1,high=100,size=(10,10))
print("The data to be plotted:\n")
print(data)
```
![image](https://github.com/user-attachments/assets/9bb5b2c4-5661-4ac6-812f-7547cd83df34)
```
sns.heatmap(data=data,annot=True)
```
![image](https://github.com/user-attachments/assets/f691a3fb-cffc-4674-bcf7-7bb26681e6b0)
```
sns.heatmap(data=data)
```
![image](https://github.com/user-attachments/assets/8032b997-21dc-40ac-9795-f5bd0aee49cc)

# Result:
  Thus,Data Visualization using seaborn python library for the given datas is successfully performed.
