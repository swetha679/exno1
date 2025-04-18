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

















        
        
        





# Result
          <<include your Result here>>
