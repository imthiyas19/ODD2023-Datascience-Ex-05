# Ex:05 Feature Generation
# AIM :
To read the given data and perform Feature Generation process and save the data to a file.

### EXPLANATION :

Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

# ALGORITHM :
# STEP 1 :
Read the given Data

# STEP 2 :
Clean the Data Set using Data Cleaning Process

# STEP 3 :
Apply Feature Generation techniques to all the feature of the data set

# STEP 4 :
Save the data to the file

# PROGRAM :
NAME : mohammed imthiyas.M
REG NO : 212222230083

## Encoding.csv :
```
import pandas as pd
df=pd.read_csv('Encoding Data.csv')
df.head()
df['ord_2'].unique()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot']
en= OrdinalEncoder(categories = [climate])
df['ord_2']=en.fit_transform(df[["ord_2"]])
df
le = LabelEncoder()
df['Nom_0'] = le.fit_transform(df[["nom_0"]])
df
!pip install --upgrade category_encoders
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data = be.fit_transform(df['bin_1'])
df  = pd.concat([df,data],axis=1)
df
be = BinaryEncoder()
data = be.fit_transform(df['bin_2'])
df  = pd.concat([df,data],axis=1)
df
```

OUTPUT :
# For encoding.csv file:


![276687262-db0bf84b-d1d2-4bbb-af0d-cc7182e4a368](https://github.com/imthiyas19/ODD2023-Datascience-Ex-05/assets/120353416/b1fb4cd4-1174-47cf-a91c-e22c977cb430)


![276687273-5e4279e4-3309-4013-8607-3fed068c8447](https://github.com/imthiyas19/ODD2023-Datascience-Ex-05/assets/120353416/bcd6b624-3e58-4a5e-8c46-8123f0f532d2)




![276687287-42184ca9-8ddb-4cf0-85c2-ece4bae32945](https://github.com/imthiyas19/ODD2023-Datascience-Ex-05/assets/120353416/47e95f93-2e7a-4d26-b4bc-ee6b6349be16)


![276687298-d1e0d943-caf6-45c0-8cca-b865282ffe9d](https://github.com/imthiyas19/ODD2023-Datascience-Ex-05/assets/120353416/5ae9715c-9688-4fd8-8259-7a8798ea5a3f)


![276687315-33706f4d-933d-4867-ac7a-5e90e95de375](https://github.com/imthiyas19/ODD2023-Datascience-Ex-05/assets/120353416/c6660c4a-8d18-454c-ab8c-efd6db79b038)



![276687324-823b6ec5-e8c7-46c3-a0a0-4171a6dfa3f8](https://github.com/imthiyas19/ODD2023-Datascience-Ex-05/assets/120353416/ffb4c7e9-25db-49b1-855b-6f45316e4803)





Data.csv :
```
import pandas as pd
df1 = pd.read_csv("data.csv")
df1.head()
df1['Ord_1'].unique()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot','Very Hot']
en= OrdinalEncoder(categories = [climate])
df1['Ord_1']=en.fit_transform(df1[["Ord_1"]])
df1
df1['Ord_2'].unique()
cl = ['High School','Diploma','Bachelors','Masters','PhD']
en= OrdinalEncoder(categories = [cl])
df1['Ord_2']=en.fit_transform(df1[["Ord_2"]])
df1
le = LabelEncoder()
df1['City'] = le.fit_transform(df1[["City"]])
df1
from category_encoders import BinaryEncoder
be = BinaryEncoder()
dat = be.fit_transform(df1['bin_1'])
df1  = pd.concat([df1,dat],axis=1)
df1
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data1 = be.fit_transform(df1['bin_2'])
df1  = pd.concat([df1,data1],axis=1)
df1
```
# OUTPUT :
# For Data.csv file:


![276687472-f25bfbc9-7e4e-4846-898f-85e69c19b5b0](https://github.com/imthiyas19/ODD2023-Datascience-Ex-05/assets/120353416/67f6aedd-ce1f-4791-a026-9127b5b29f32)

![276687488-cc5742bf-36ef-4561-ba23-c8960c0bf418](https://github.com/imthiyas19/ODD2023-Datascience-Ex-05/assets/120353416/cf1ef49f-91fa-4520-ae04-5af3de4d8f4a)


![276687500-efa22e92-f11d-428a-92f6-3def929f8473](https://github.com/imthiyas19/ODD2023-Datascience-Ex-05/assets/120353416/59b1a7c7-a3b2-417b-a618-8ac54e07e1a2)


![276687511-febf5e94-6f8f-42a8-97f7-87b35b1424ea](https://github.com/imthiyas19/ODD2023-Datascience-Ex-05/assets/120353416/b37d2929-d8a7-4b88-8ecd-d949e781502d)




![276687527-818f29dc-3049-4579-aa53-b4e670ac3c25](https://github.com/imthiyas19/ODD2023-Datascience-Ex-05/assets/120353416/0075d328-cbb2-4fbf-884a-5d1b2cf84580)



![276687534-a11b5a21-ddbf-4131-b82a-061348df0a3c](https://github.com/imthiyas19/ODD2023-Datascience-Ex-05/assets/120353416/d32e9342-3abd-42c4-abc6-8d2f3ca51546)





![276687540-91ad2490-92db-4a14-9e6f-2b17f6312b92](https://github.com/imthiyas19/ODD2023-Datascience-Ex-05/assets/120353416/40c941be-70a1-4787-b347-ce4711bd7bff)



# BMI.csv file:
```
import pandas as pd
df2 = pd.read_csv("/content/bmi.csv")
df2.head()
be = BinaryEncoder()
data2 = be.fit_transform(df2['Gender'])
df2  = pd.concat([df2,data2],axis=1)
df2
df2 = pd.get_dummies(df2, prefix=['Index'] ,columns=['Index'])
df2
```

OUTPUT :
For bmi.csv file:


![276687724-51f671c1-c466-41db-a2d9-6e9dc9617431](https://github.com/imthiyas19/ODD2023-Datascience-Ex-05/assets/120353416/281269f5-bef1-4a0f-9995-52614f31a217)




![276687728-3817d8db-da9c-4c4c-8b7a-bdb2699070ba](https://github.com/imthiyas19/ODD2023-Datascience-Ex-05/assets/120353416/48b4ba0a-1d80-47ed-a9e0-9bce529ed028)




![276687752-e8405041-1b45-4cea-9abc-d791b4a3cdf8](https://github.com/imthiyas19/ODD2023-Datascience-Ex-05/assets/120353416/c6a2b854-ade1-4185-a0b0-49ba158ba66a)

RESULT:
The Feature Generation process was performed and saved the data to a file.
