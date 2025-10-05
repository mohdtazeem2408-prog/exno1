# Exno:1 Data Cleaning Process

### Name : MOHAMED TAZEEM R
### Reg No: 25012330

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


import pandas as pd
df  = pd.read_csv("Data_set.csv")
df


<img width="1195" height="383" alt="image" src="https://github.com/user-attachments/assets/a3a311d2-2608-415a-b9a6-167e77a9d4ae" />


df.describe()


<img width="760" height="262" alt="Screenshot 2025-08-19 105128" src="https://github.com/user-attachments/assets/09c26c84-5dbe-498f-9203-16cac512b590" />


df.info()


<img width="515" height="318" alt="Screenshot 2025-08-19 105227" src="https://github.com/user-attachments/assets/2878fceb-e947-47d4-b90f-5110d0e5d7f1" />


df.head(4)


<img width="1179" height="159" alt="Screenshot 2025-08-19 105312" src="https://github.com/user-attachments/assets/26787dca-100e-49c8-ba84-ee6d2d92f11d" />


df.tail(3)


<img width="1164" height="119" alt="Screenshot 2025-08-19 105509" src="https://github.com/user-attachments/assets/f10b7234-6bda-4ffe-bc7d-057c8dbfa2c6" />


df.isnull()


<img width="1029" height="380" alt="Screenshot 2025-08-19 105558" src="https://github.com/user-attachments/assets/24fc0909-d8e9-4cca-968a-8e654e2bd1b2" />


df.notnull()


<img width="1015" height="379" alt="Screenshot 2025-08-19 105645" src="https://github.com/user-attachments/assets/ee34eb82-bbf9-4d35-88db-c13311dd1842" />


df.isnull().sum()


<img width="362" height="194" alt="Screenshot 2025-08-19 105724" src="https://github.com/user-attachments/assets/25d86168-5de0-47c3-9dd2-fb617144107a" />


df.notnull().sum()


<img width="394" height="203" alt="Screenshot 2025-08-19 105754" src="https://github.com/user-attachments/assets/369df0ef-2513-4abe-a1e5-d13bdfd75ce6" />


df.shape


<img width="194" height="43" alt="Screenshot 2025-08-19 105824" src="https://github.com/user-attachments/assets/34777354-5b88-409d-a3ea-99a7dc0fd0e1" />


df[df['rating'] > 8]


<img width="1207" height="533" alt="Screenshot 2025-08-19 105920" src="https://github.com/user-attachments/assets/800a211f-2765-4fe4-b720-0cdd870e0b2d" />


df[df['num_episodes'] > 20]


<img width="1003" height="562" alt="Screenshot 2025-08-19 110001" src="https://github.com/user-attachments/assets/4272563a-31bb-4acf-b1c9-20f464003c3f" />


df.iloc[2:5 , :-3]


<img width="856" height="129" alt="Screenshot 2025-08-19 110032" src="https://github.com/user-attachments/assets/b1c18c70-bb7d-4ea5-a394-b8d5e94e8ae0" />


df.iloc[[6,7,8],[1,2,3]]


<img width="464" height="122" alt="Screenshot 2025-08-19 110100" src="https://github.com/user-attachments/assets/030c9e0a-6789-42c7-bbf5-dc997f51cb8c" />


df.loc[3:5 , ['country' , 'num_episodes']]


<img width="347" height="131" alt="Screenshot 2025-08-19 110123" src="https://github.com/user-attachments/assets/83d5998d-b5bf-4bac-ab08-c570409cb32b" />


df['country'].value_counts()


<img width="348" height="86" alt="Screenshot 2025-08-19 110148" src="https://github.com/user-attachments/assets/87e59b15-62d6-4446-aff6-f04ba8b35e76" />


df.count()


<img width="414" height="201" alt="Screenshot 2025-08-19 110216" src="https://github.com/user-attachments/assets/4c8c6711-d662-431a-8803-e3db52de9ac8" />


df.dropna(axis = 1)


<img width="508" height="381" alt="Screenshot 2025-08-19 110242" src="https://github.com/user-attachments/assets/07b6f012-9f6f-4982-915d-48693ec0e647" />


df.fillna(0)


<img width="1199" height="384" alt="Screenshot 2025-08-19 110413" src="https://github.com/user-attachments/assets/796ed153-0d5b-449f-93a9-d38a682300b1" />


df.fillna(method = 'bfill')


<img width="1204" height="378" alt="Screenshot 2025-08-19 110441" src="https://github.com/user-attachments/assets/05806ffc-fae5-4147-be33-956e9ca58371" />


df.interpolate()


<img width="1191" height="384" alt="Screenshot 2025-08-19 110508" src="https://github.com/user-attachments/assets/f0a7f936-186b-47ee-9cc6-6e3f70a31e48" />


ffil = df.fillna(method = 'ffill') 
ffil


<img width="1197" height="381" alt="Screenshot 2025-08-19 110537" src="https://github.com/user-attachments/assets/c09b380a-a381-4587-a295-a362feba017e" />


bfil = df.fillna(method = 'bfill') 
bfil


<img width="1199" height="391" alt="Screenshot 2025-08-19 110605" src="https://github.com/user-attachments/assets/f2a77e5b-5b5c-4564-8927-cab38599f7e6" />


m = df.num_episodes.mean() 
m


<img width="214" height="30" alt="Screenshot 2025-08-19 110639" src="https://github.com/user-attachments/assets/efddacbb-d4c8-4bcf-8310-843175104b75" />


m = df.fillna(df['num_episodes'].mean()) 
m


<img width="1212" height="544" alt="Screenshot 2025-08-19 110710" src="https://github.com/user-attachments/assets/8afe9182-0f3b-4cda-80db-cb07aa6cdb77" />


fmean = df['lifetime_popularity_rank'].fillna(value=df['lifetime_popularity_rank'].mean()) 
fmean


<img width="625" height="244" alt="Screenshot 2025-08-19 110736" src="https://github.com/user-attachments/assets/75e699cb-fead-408c-9d70-dc895208c9d4" />


df = pd.read_csv('SAMPLEIDS.csv') 
df


<img width="918" height="636" alt="Screenshot 2025-08-19 110806" src="https://github.com/user-attachments/assets/fd46162b-d4ec-47c0-97db-24c0dafd8d2b" />


df['GENDER'].value_counts()


<img width="341" height="65" alt="Screenshot 2025-08-19 110830" src="https://github.com/user-attachments/assets/d3d7d69f-5cd9-4e95-8019-3c12fac6641f" />


x1 = df.dropna(how='any') 
x1


<img width="930" height="409" alt="Screenshot 2025-08-19 110858" src="https://github.com/user-attachments/assets/b338c961-28c3-4b68-906d-8e26899d0ed3" />


res = df.dropna(subset=['M1','M2','M3','M4'],how='any') 
res


<img width="918" height="402" alt="Screenshot 2025-08-19 110923" src="https://github.com/user-attachments/assets/8b7c3c6c-1a2e-48bc-b94a-33160778bcc6" />


df=pd.read_csv('heights.csv') 
df


<img width="305" height="429" alt="Screenshot 2025-08-19 110952" src="https://github.com/user-attachments/assets/90e475a1-4f95-459b-b53c-4cb20fac22e4" />


import seaborn as sns
import matplotlib.pyplot as plt
sns.boxplot(data=df)
plt.show()


<img width="687" height="464" alt="Screenshot 2025-08-19 111015" src="https://github.com/user-attachments/assets/a77e1218-6a87-42c1-8840-9d449101f876" />


sns.scatterplot(data=df)


<img width="741" height="496" alt="Screenshot 2025-08-19 111039" src="https://github.com/user-attachments/assets/5c29c48e-2152-492f-831b-358cbe005088" />


max = df['height'].quantile(0.75) 
min = df['height'].quantile(0.25)
iqr = max-min 
iqr


<img width="280" height="31" alt="Screenshot 2025-08-19 111104" src="https://github.com/user-attachments/assets/71fd1e79-668d-4818-9d7a-1ed5ade1ad40" />


lb = min-1.5
ub = max+1.5
iqr 
outliers = df[(df['height']<lb)|(df['height']>ub)] 
print("Lower bound:",lb)
print("Upper bound:",ub)
print("Outliers:",outliers)


<img width="327" height="103" alt="Screenshot 2025-08-19 111136" src="https://github.com/user-attachments/assets/83f7e893-1180-486e-86ed-bd90b6b91a28" />


import numpy as np 
from scipy import stats
z = np.abs(stats.zscore(df['height'])) 
z


<img width="362" height="293" alt="Screenshot 2025-08-19 111205" src="https://github.com/user-attachments/assets/caeb8d17-4c57-41fe-aeb6-0f23da7ab57e" />


df1 = df[z<3] 
df1


<img width="304" height="401" alt="Screenshot 2025-08-19 111236" src="https://github.com/user-attachments/assets/c71cda29-9478-460c-9a0a-f4bc1ee6bbdd" />



# Summary
 Load & explore data (describe, info, head, tail).

 Check for missing values (isnull, notnull, sum).

 Filter rows, select subsets of data (iloc, loc, conditions).

 Handle missing data (drop, fill, interpolate, mean imputation).

 Explore categorical data (value_counts).

 Work with multiple datasets (Data_set.csv, SAMPLEIDS.csv, heights.csv).

 Visualize distributions (boxplot, scatterplot).

 Detect & remove outliers (IQR method, Z-score).

# Result
Thus the given data has been read, cleaned and the data has been saved to a file.
