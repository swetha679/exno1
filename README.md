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
df=pd.read_csv("/content/SAMPLEIDS (1).csv")
df
```

          
![Screenshot 2025-04-18 200314](https://github.com/user-attachments/assets/d86702f6-f275-4ff7-a86e-1477bd830bb2)
![Screenshot 2025-04-18 200334](https://github.com/user-attachments/assets/c24b8d21-f001-46c7-a1ef-574a438ff2ff)



```
df.shape
```

 
 ![Screenshot 2025-04-18 201213](https://github.com/user-attachments/assets/5534a73c-06da-4dea-8bb9-b2817bc9c099)

 ```
 df.describe()
```
```
df.info()
```

![Screenshot 2025-04-18 202010](https://github.com/user-attachments/assets/8e943d6a-705f-42fe-bba4-f16c45290164)

```
df.head(10)
```

![Screenshot 2025-04-18 202059](https://github.com/user-attachments/assets/b639e513-d6a2-40b0-82d5-18b87f9646e0)

```
df.tail(10)
```

![Screenshot 2025-04-18 202144](https://github.com/user-attachments/assets/4125bf73-406b-42bf-8e00-7a9d84e98842)

```
df.isna().sum()
```

![Screenshot 2025-04-18 202239](https://github.com/user-attachments/assets/eed2ef6e-8ec5-49d1-9266-eb9c54036a9e)

```
df.dropna(how='any').shape
```

![Screenshot 2025-04-18 202320](https://github.com/user-attachments/assets/37c0703e-614d-4ce2-9b30-66814a89057d)

```
 x=df.dropna(how='any')
 x
```

![Screenshot 2025-04-18 202409](https://github.com/user-attachments/assets/a6576a14-0c77-44f6-b4cc-ddeacebfb189)

```
mn=df.TOTAL.mean()
mn
```

![Screenshot 2025-04-18 202504](https://github.com/user-attachments/assets/7bfa870e-554d-409c-87c2-ee89cf53296d)

```
df.TOTAL.fillna(mn,inplace=True)
df
```

![Screenshot 2025-04-18 202630](https://github.com/user-attachments/assets/5dc6afd1-95c7-4b59-913d-5f6db1787bc3)
![Screenshot 2025-04-18 202644](https://github.com/user-attachments/assets/d9cb1de5-4bd3-4afb-bf4f-eca0e3198981)

```
df.isnull().sum()
```

![Screenshot 2025-04-18 202739](https://github.com/user-attachments/assets/1a6c7311-05e1-4fa9-893a-d16fd72668aa)

```
df.M1.fillna(method='ffill',inplace=True)
df
```

![Screenshot 2025-04-18 202924](https://github.com/user-attachments/assets/56882a46-3fce-4a74-b5c1-c62344206934)
![Screenshot 2025-04-18 202937](https://github.com/user-attachments/assets/d7969f7d-05a0-4989-b223-b364c13fa1e4)

```
 df.isnull().sum()
```

![Screenshot 2025-04-18 203049](https://github.com/user-attachments/assets/566cb180-8b85-47c2-a2bf-132a99242f7a)

```
df.M2.fillna(method='ffill',inplace=True)
df
```

![Screenshot 2025-04-18 203143](https://github.com/user-attachments/assets/c397a28a-528d-4050-a0bf-5bc79cd813fb)
![Screenshot 2025-04-18 203153](https://github.com/user-attachments/assets/f5305570-d119-480f-9526-aa831411364c)

```
df.isna().sum()
```

![Screenshot 2025-04-18 203249](https://github.com/user-attachments/assets/ca5e9633-33ae-4bf7-a70f-df93a4520ee3)

```
df.M3.fillna(method='ffill',inplace=True)
df
```

![Screenshot 2025-04-19 064353](https://github.com/user-attachments/assets/bd6a9138-bf70-4097-b365-3eac14fa5234)
![Screenshot 2025-04-19 064424](https://github.com/user-attachments/assets/d741c370-f708-444f-a5c1-1ad20b42e72f)


```
df.isnull().sum()
```

![Screenshot 2025-04-19 064512](https://github.com/user-attachments/assets/459360f4-82af-413d-9bd5-428e44f193c7)

```
df.duplicated()
```

![Screenshot 2025-04-19 064608](https://github.com/user-attachments/assets/4a6145c1-f560-4c3c-a8bc-ea3e5df29365)
![Screenshot 2025-04-19 064648](https://github.com/user-attachments/assets/5523e84d-374d-423a-a140-9e28c2a597f7)


```
df.drop_duplicates(inplace=True)
df
```

![Screenshot 2025-04-19 064745](https://github.com/user-attachments/assets/00b5d38a-bc99-4c7c-83ed-5ba8e3142f37)
![Screenshot 2025-04-19 064808](https://github.com/user-attachments/assets/c90ab56b-7251-45b5-90cb-e2e027301f47)


```
df['DOB']
```

![Screenshot 2025-04-19 064927](https://github.com/user-attachments/assets/f19c11d4-a468-4b08-aee3-0847141467b0)
![Screenshot 2025-04-19 064940](https://github.com/user-attachments/assets/b577752b-79cc-41f8-80ff-3ded5c3e7319)

```
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```



![Screenshot 2025-04-19 065043](https://github.com/user-attachments/assets/79c7a4db-c567-41db-b9ad-c557df7f8dea)


```
df.dropna(inplace=True)
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```

![image](https://github.com/user-attachments/assets/0b2cdb9b-69ce-4d5c-ab38-b8e0dd2dacf5)

```
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
df=pd.DataFrame(age)
df
 ```

![Screenshot 2025-04-19 065346](https://github.com/user-attachments/assets/b63df5ee-53f0-4a24-aad0-d83d1eea22b9)

```
sns.boxplot(data=df)
```

![image](https://github.com/user-attachments/assets/4af0d2c0-d153-448a-939b-9bcf112167a5)

```
sns.scatterplot(data=df)
```

![Screenshot 2025-04-19 065550](https://github.com/user-attachments/assets/cd6467e7-b34f-4bf3-b5cc-d6aa3610d66d)


```
q1=df.quantile(0.25)
q2=df.quantile(0.5)
q3=df.quantile(0.75)
iqr=q3-q1
iqr
```

![Screenshot 2025-04-19 065726](https://github.com/user-attachments/assets/bc28a23b-5c3d-42df-b326-c130de5eb4dd)

```
import numpy as np
Q1 = np.percentile(df, 25)
Q3=np.percentile(df,75)
IQR=Q3-Q1
IQR
```

![Screenshot 2025-04-19 065919](https://github.com/user-attachments/assets/ff270dc8-ce1f-4dbc-96d7-b4c5f026418a)

```
lower_bound=Q1-1.5*IQR
upper_bound=Q3+1.5*IQR
lower_bound
```

![Screenshot 2025-04-19 070036](https://github.com/user-attachments/assets/5064b62a-095c-4d85-9912-7a23a0bee6e0)

```
upper_bound
```

![Screenshot 2025-04-19 070124](https://github.com/user-attachments/assets/a0b2dcc3-05fd-441e-9ad8-23253d3cd78c)

```
outliers=[x for x in age if x<lower_bound or x>upper_bound]
print("Q1:",Q1)
print("Q3:",Q3)
print("IQR:",IQR)
print("Lower Bound:",lower_bound)
print("Upper Bound:",upper_bound)
print("Outliers:",outliers)
```

![Screenshot 2025-04-19 070230](https://github.com/user-attachments/assets/7324a5f8-0572-4124-bfb2-1f383713074e)

```
df=df[((df>=lower_bound)&(df<=upper_bound))]
df
```

![Screenshot 2025-04-19 070330](https://github.com/user-attachments/assets/64714387-8a0a-4727-8ec8-c704efb36bfc)

 ```
df=df.dropna()
df
```

![Screenshot 2025-04-19 070510](https://github.com/user-attachments/assets/65ed7d9a-5768-410d-95b8-f885f084d035)

```
sns.boxplot(data=df)
```

![image](https://github.com/user-attachments/assets/e6fd24ad-2129-4d0c-a884-39eae32edb6b)

```
sns.scatterplot(data=df)
```

![image](https://github.com/user-attachments/assets/fb1bbd2f-e975-4fb9-b99c-c1efd80439df)

```
data=[1,2,2,2,3,1,1,15,2,2,2,3,1,1,2]
mean=np.mean(data)
std=np.std(data)
print('mean of the dataset is',mean)
print('std.deviation is',std)

```

![Screenshot 2025-04-19 070813](https://github.com/user-attachments/assets/16572332-9f38-4a62-bedb-10e92166d963)

```
threshold=3
outlier=[]
for i in data:
z=(i-mean)/std
if z>threshold:
outlier.append(i)
print('outlier in dataset is',outlier)

```

![Screenshot 2025-04-19 070903](https://github.com/user-attachments/assets/fedbef1a-e0da-4369-9125-5aedb4eca173)

```
 import pandas as pd
 import numpy as np
 import seaborn as sns
 from scipy import stats
 data={'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,
 66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
 df=pd.DataFrame(data)
 df
 ```

![image](https://github.com/user-attachments/assets/86957bc9-a10a-46a4-b299-daafc11d5752)
![Screenshot 2025-04-19 071020](https://github.com/user-attachments/assets/eae29ffd-7241-453a-a703-cf979970512f)

```
z=np.abs(stats.zscore(df))
print(df[z['weight']>3])
```

![Screenshot 2025-04-19 071116](https://github.com/user-attachments/assets/c9f89693-7d9d-414f-aa1f-8dcc537b3205)














































        
        
        





# Result
          <<include your Result here>>
