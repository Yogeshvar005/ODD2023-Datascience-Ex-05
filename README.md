# Ex:05 Feature Generation
## AIM
To read the given data and perform Feature Generation process and save the data to a file.

## Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

## ALGORITHM
### STEP 1
Read the given Data.

### STEP 2
Clean the Data Set using Data Cleaning Process.

### STEP 3
Apply Feature Generation techniques to all the feature of the data set.

### STEP 4
Save the data to the file.

## CODE :
```
Developed by : Yogeshvar M           
Reg No : 212222230180
```
## Data.csv:
```
import pandas as pd
df=pd.read_csv("data.csv")
print(df)

import category_encoders as ce
be=ce.BinaryEncoder()
df1=be.fit_transform(df["bin_1"])
df["bin_1"] = be.fit_transform(df["bin_1"])
df1

be=ce.BinaryEncoder()
df2=be.fit_transform(df["bin_2"])
df["bin_2"] = be.fit_transform(df["bin_2"])
df2

df1=df.copy()

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder,OneHotEncoder
import category_encoders as ce
be=ce.BinaryEncoder()
ohe=OneHotEncoder(sparse=False)
le=LabelEncoder()
oe=OrdinalEncoder()

df1["City"] = ohe.fit_transform(df1[["City"]])
temp=['Cold','Warm','Hot','Very Hot']
oe1=OrdinalEncoder(categories=[temp])
df1['Ord_1'] = oe1.fit_transform(df1[["Ord_1"]])
edu=['High School','Diploma','Bachelors','Masters','PhD']
oe2=OrdinalEncoder(categories=[edu])
df1['Ord_2']= oe2.fit_transform(df1[["Ord_2"]])
df1
```
## SCALING:
```
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df2=pd.DataFrame(sc.fit_transform(df1),columns=(['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target']))
df2

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df3=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df3

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df4=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df4

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df5=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df5
```
## Encoding data:
```
import pandas as pd
df=pd.read_csv("Encoding Data.csv")
df
```
## GENERATION:
```
import category_encoders as ce
be=ce.BinaryEncoder()
ndf=be.fit_transform(df["bin_1"])
df["bin_1"] = be.fit_transform(df["bin_1"])
ndf

be=ce.BinaryEncoder()
ndf2=be.fit_transform(df["bin_2"])
df["bin_2"] = be.fit_transform(df["bin_2"])
ndf2

df1=df.copy()

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
le=LabelEncoder()
oe=OrdinalEncoder()

df1["nom_0"] = oe.fit_transform(df1[["nom_0"]])
temp=['Cold','Warm','Hot']
oe2=OrdinalEncoder(categories=[temp])
df1['ord_2'] = oe2.fit_transform(df1[['ord_2']])
df1
```
## SCALING:
```
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df0=pd.DataFrame(sc.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df0

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df2=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df2

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df3=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df3

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df4=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df4
```
## OUTPUT :
## (i) Data.csv
![273362000-387df8d7-ed25-443b-8be1-0d1bfdadaed5](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-05/assets/113497367/1ffa9116-f73f-4576-8833-688c03ce2938)       
![273362517-735bf477-174c-4ba7-91f4-9f33f817cb94](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-05/assets/113497367/e29e5532-d45d-4884-9a3a-9d5e8297b3e9)      
![273362522-ab54e0b8-7434-49a5-96cc-4902b801df42](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-05/assets/113497367/c993334a-dcca-4982-ab32-dfc525b0cd8c)      
![273362537-e3c82327-1601-4155-8cda-a0efdb142f2d](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-05/assets/113497367/9f3c246e-de22-4ac7-ba51-2117287c78e4)    

## Minmax scaling:
![273362126-2c6efcda-1cd1-4790-9365-59844c6998a1](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-05/assets/113497367/f8eeda58-b664-470e-9734-609dd235f177)
## Standard scaling:
![273362143-a8d5c162-3e69-446b-90a6-c7bfaf6e8009](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-05/assets/113497367/f16166a2-579f-4f81-a6bf-e23bcd2595a1)

## Maxabs scaling:
![273362166-ec643798-a4c5-4714-96ce-1dcb6e88ddbd](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-05/assets/113497367/6d840b85-bae5-446b-8c26-2cf6bc3c50e2)
## Robust scaling:
![273362186-7e617f51-ec9f-4860-aefd-d5ae9a67612c](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-05/assets/113497367/39cc81ae-d452-4bff-9f31-e9fc77a396c0)
## (ii) Encoding data.csv
![273362244-81f07773-a53c-43ca-bdc8-5b020bbb4df6](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-05/assets/113497367/5a1a3704-04f0-4ba3-b076-d4f3507eafb6)    
![273362249-462a98d7-12dc-4292-910a-1e3cbec00d39](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-05/assets/113497367/f6fbed76-b551-426d-b356-d2b06614562a)      
![273362256-bb34642d-b8b0-4266-84b9-d1df47cb08bb](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-05/assets/113497367/0e535980-03b7-4df8-8198-115700c5c36d)      
## Minmax scaler:
![273362270-c418d508-2c0b-4131-b491-2ef8cb2a96e3](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-05/assets/113497367/b90b49b7-6232-4b0e-ac26-a1dcab1b14a5)
## Standard scaler:
![273362339-d1d62e7d-e4dc-4230-9662-6afa7e2c5988](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-05/assets/113497367/6729a343-6c2e-4af1-b409-fd2b6599616b)
## Maxabs scaler:
![273362351-64000c89-263c-4962-abfe-820a2833caf8](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-05/assets/113497367/b6eb7dc7-1470-4e65-813b-dc04a5572e90)
## Robust scaler:
![273362383-311a688a-aab1-4744-9e60-f215e16396e1](https://github.com/Yogeshvar005/ODD2023-Datascience-Ex-05/assets/113497367/5088953d-e721-4eda-a82e-e512266d96e7)
## Result:
Thus the Feature Generation and Feature Scaling process is applied to the given data set.
