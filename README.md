# DS---EX-02

AIM:
  To perform Exploratory Data Analysis on the given data set.
EXPLANATION:
The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

CODING AND OUTPUT


import pandas as pd 
import numpy as np 
import matplotlib.pyplot as plt
import seaborn as sns  
df=pd.read_csv("titanic_dataset.csv") 
df

<img width="1452" height="420" alt="image" src="https://github.com/user-attachments/assets/642a850d-309b-4855-ba8b-017ace99be88" />

df.info()

<img width="1241" height="271" alt="image" src="https://github.com/user-attachments/assets/37de3b81-3cef-401c-b098-8dbc3045721e" />

df.shape
<img width="887" height="60" alt="image" src="https://github.com/user-attachments/assets/f03b69b7-2382-497a-b76b-17c762843cea" />

df.set_index("PassengerId",inplace=True) 
df.describe()
<img width="1203" height="252" alt="image" src="https://github.com/user-attachments/assets/17dc5589-bb37-4873-ab2d-4cb9c1d4164c" />

df.shape
<img width="967" height="61" alt="image" src="https://github.com/user-attachments/assets/0da309e1-9b2d-4853-a512-f36762874b18" />

df.nunique()
<img width="1110" height="323" alt="image" src="https://github.com/user-attachments/assets/22dfb855-0c3f-4bbe-863d-2ea3ee221acc" />

df["Survived"].value_counts()
<img width="786" height="161" alt="image" src="https://github.com/user-attachments/assets/649fc570-8b9b-42fb-8d42-af59d4000769" />

per=(df["Survived"].value_counts()/df.shape[0]*100).round(2) 
per
<img width="1107" height="175" alt="image" src="https://github.com/user-attachments/assets/82ca0514-f913-48a5-a71c-73953770e43c" />

sns.countplot(data=df,x="Survived")
<img width="1338" height="367" alt="image" src="https://github.com/user-attachments/assets/252db39b-8598-4f35-bd05-115cc3abfacc" />

df
<img width="1306" height="387" alt="image" src="https://github.com/user-attachments/assets/f7c5c256-02c0-4bb2-b36e-ec2a826e1c0e" />

df.Pclass.unique()
<img width="813" height="52" alt="image" src="https://github.com/user-attachments/assets/1a2e7316-5afa-4a25-a89a-b93e858f17f6" />

df.rename(columns={'Sex':'Gender'},inplace=True) 
df
<img width="1307" height="391" alt="image" src="https://github.com/user-attachments/assets/18ff00bd-a401-4666-98e8-dfe6f87f9fc3" />

sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
<img width="1126" height="393" alt="image" src="https://github.com/user-attachments/assets/9cac0fa9-2b16-441e-89ec-40beace6f4bc" />

sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
<img width="1042" height="397" alt="image" src="https://github.com/user-attachments/assets/4a220125-0d0c-4a91-b166-734767112df3" />

df.boxplot(column="Age",by="Survived")
<img width="1193" height="382" alt="image" src="https://github.com/user-attachments/assets/8389f5be-b358-4971-b8f4-6a37938e6093" />

sns.scatterplot(x=df["Age"],y=df["Fare"])
<img width="1301" height="352" alt="image" src="https://github.com/user-attachments/assets/a9f54f45-2bc5-48f7-96c0-1c5256d19303" />

sns.jointplot(x="Age",y="Fare",data=df)
<img width="1207" height="465" alt="image" src="https://github.com/user-attachments/assets/93e4f743-bf49-4887-909b-a7e3b4ec6dac" />

fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
<img width="1337" height="367" alt="image" src="https://github.com/user-attachments/assets/5f017869-99b6-4664-b3e4-0c0c6a5531c0" />

sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
<img width="1455" height="393" alt="image" src="https://github.com/user-attachments/assets/440fbcfa-fdb2-4848-8093-37b82ab7ffc4" />

corr = df.corr(numeric_only=True)

sns.heatmap(corr, annot=True)
<img width="1256" height="390" alt="image" src="https://github.com/user-attachments/assets/59974baf-8bfa-409e-bab9-5fe12a47601b" />

sns.pairplot(df)
<img width="1560" height="721" alt="image" src="https://github.com/user-attachments/assets/9b8bc922-1dc8-4fdd-afcc-1b434151427a" />


RESULT
    We have performed Exploratory Data Analysis on the given data set successfully
