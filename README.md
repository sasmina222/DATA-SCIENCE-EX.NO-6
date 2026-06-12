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
import seaborn as sns
import matplotlib.pyplot as plt
df = sns.load_dataset("tips")
df
```
<img width="560" height="504" alt="image" src="https://github.com/user-attachments/assets/eb8cc6c6-ce7f-4059-a34a-cd13fe589a70" />

sns.lineplot(x="total_bill", y="tip", data=df, hue="sex", linestyle="solid", legend="auto", palette="Set1")

<img width="723" height="573" alt="image" src="https://github.com/user-attachments/assets/54dea930-e4bb-4e55-a981-5b8afca72500" />

~~~
x = [1,2,3,4,5]
y1 = [3,5,2,6,1]
y2 = [1,6,4,3,8]
y3 = [5,2,7,1,4]
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel('Y Label')
~~~
<img width="715" height="602" alt="image" src="https://github.com/user-attachments/assets/184f0100-1e8f-4fa5-8244-3ab473e69a2b" />
~~~
tips = sns.load_dataset("tips")
avg_total_bill = tips.groupby("day")["total_bill"].mean()
avg_tip = tips.groupby("day")["tip"].mean()
plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index, avg_total_bill,label='Total Bill')
p2=plt.bar(avg_tip.index, avg_tip,bottom=avg_total_bill, label='Tip')
plt.xlabel("Day of the week")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Day")
plt.legend()
plt.show()
~~~
<img width="768" height="704" alt="image" src="https://github.com/user-attachments/assets/7dee757d-1379-40eb-841e-d8a9bf41d89c" />
~~~
import seaborn as sns
df = sns.load_dataset("tips")
sns.barplot(x="day", y="total_bill", hue="sex",data=df,palette='Set3')
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Total Bill by Day and Gender")
~~~
<img width="717" height="596" alt="image" src="https://github.com/user-attachments/assets/50bd88ce-00ad-4d0f-9d85-c272766e752b" />
~~~
import seaborn as sns
df = sns.load_dataset("tips")
sns.scatterplot(x="total_bill", y="tip", hue="sex",data=df,palette='Set1')
plt.xlabel("Total Bill")
plt.ylabel("Tip")
plt.title("Scatter Plot of Total Bill vs Tip Amount")
~~~
<img width="713" height="590" alt="image" src="https://github.com/user-attachments/assets/51d16f7f-dd43-40b9-bf2e-abbf007fb0d4" />
~~~
sns.histplot(data=df,x="total_bill",hue="smoker",kde=True,palette='Set1')
plt.xlabel("Total Bill")
plt.ylabel("Frequency")
plt.title("Distribution of Total Bill by Gender")
~~~
<img width="716" height="597" alt="image" src="https://github.com/user-attachments/assets/1642e527-a406-493b-b623-918cb3985a37" />
~~~
import seaborn as sns
import pandas as pd
df = sns.load_dataset('tips')
sns.boxplot(x='day', y='total_bill',hue='sex',data=df, palette='Set2')
~~~
<img width="717" height="569" alt="image" src="https://github.com/user-attachments/assets/0710cb08-b089-42db-a423-4a460311c9d4" />
~~~
sns.violinplot(x="day",y="total_bill",hue="smoker",data=tips,linewidth=2,width=0.6,palette="Set1",inner="quartile")
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
~~~
<img width="709" height="599" alt="image" src="https://github.com/user-attachments/assets/42be2cad-5e08-486f-9d8e-bfe8e0ee7c35" />
~~~
import seaborn as sns
sns.set(style="whitegrid")
tip = sns.load_dataset("tips")
sns.violinplot(x="day", y="tip", data=tip, palette="Set2")
~~~
<img width="743" height="699" alt="image" src="https://github.com/user-attachments/assets/192d4990-5190-4eca-b4a3-a5663b805c7f" />
~~~
import seaborn as sns
sns.set(style="whitegrid")
tip = sns.load_dataset("tips")
sns.violinplot(x=tip["total_bill"],palette="Set1")
~~~
<img width="760" height="698" alt="image" src="https://github.com/user-attachments/assets/39777202-6df5-4308-96d0-fdebcbed6d1b" />
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple="layer",linewidth=3,palette="Set2",alpha=0.8)
<img width="762" height="583" alt="image" src="https://github.com/user-attachments/assets/a7c12851-ef3e-42dc-aac9-a128632e44bf" />
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple="stack",linewidth=3,palette="Set3",alpha=0.8)
<img width="753" height="582" alt="image" src="https://github.com/user-attachments/assets/aebe62d8-0e05-454f-b06a-339df34945dc" />
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple="fill",linewidth=3,palette="Set1",alpha=0.8)
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple="fill",linewidth=3,palette="Set1",alpha=0.8)
~~~
import seaborn as sns
tip = sns.load_dataset("tips")
num = tips.select_dtypes(include=['float64','int64']).columns
corr = tips[num].corr()
sns.heatmap(corr,annot=True,cmap='YlGnBu')
~~~
<img width="676" height="561" alt="image" src="https://github.com/user-attachments/assets/c0a26315-4d56-473f-8f6d-7d3498ec380e" />

# Result:
 Include your result here
