# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![output](./output1.png)

```
df.head()
```
![output](./output2.png)
```
df.tail()
```
![output](./output3.png)
```
df.describe()
```
![output](./output4.png)
```
df.info()
```
![output](./output5.png)
```
df.shape()
```
![output](./output6.png)
```
df.isnull().sum()
```
![output](./output7.png)
```
df.nunique()
```
![output](./output8.png)
```
df.['GENDER'].value_counts()
```
![output](./output9.png)
```
mn=df.TOTAL.mean()
mn
```
![output](./output10.png)
```
df.TOTAL.fillna(mn,inplace=True)
df
```
![output](./output11.png)
```
x=df.M4.mean()
x
```
![output](./output12.png)
```
df.M4.fillna(x,inplace=True)
df
```
![output](./output13.png)
```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![output](./output22.png)
```
sns.boxplot(data=af)
```
![output](./output23.png)
```
sns.scatterplot(data=df)
```
![output](./output24.png)
```
q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
```
![output](./output31.png)
```
print("Q1:",Q1)
print("Q3:",Q3)
print("IQR:",IQR)
print("Lower bound:",lower_bound)
print("Upper bound:",upper_bound)
print("Outliers:",outliers)
```
![output](./output32.png)
```
af=af[((af>=lower_bound)&(af<=upper_bound))]
af
```
![output](./output25.png)
```
af.dropna()
```
![output](./output26.png)
```
sns.boxplot(data=af)
```
![output](./output27.png)
```
sns.scatterplot(data=af)
```
![output](./!output28.png)
```
data={'weight':[12, 15, 18, 21, 24, 27, 30, 33, 36, 39, 42, 45, 48, 51, 54, 57, 60, 63, 66, 69,202, 72, 75, 78, 81, 84,232, 87, 90, 93, 96, 99, 258]}
df=pd.DataFrame(data)
df
```
![output](./output29.png)
```
z=np.abs(stats.zscore(df))
z
```
![output](./output30.png)
# Result
Thus the given program executed successfully.