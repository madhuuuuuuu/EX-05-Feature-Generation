# EX-05-Feature-Generation


## AIM
To read the given data and perform Feature Generation process and save the data to a file. 

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Generation techniques to all the feature of the data set
### STEP 4
Save the data to the file


# CODE

import pandas as pd

df=pd.read_csv("/content/data[1].csv")

df.info()

df.isnull().sum()

from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

df['Ord_2'] = le.fit_transform(df['Ord_2'])

sns.set(style ="darkgrid")

sns.countplot(df['Ord_2'])

from sklearn.preprocessing import OneHotEncoder

enc = OneHotEncoder()

enc = enc.fit_transform(df[['City']]).toarray()

encoded_colm = pd.DataFrame(enc)

df = pd.concat([df, encoded_colm], axis=1)

df = df.drop(['City'], axis=1)

df.head(10)

df = pd.get_dummies(df, prefix=['Ord_2'], columns=['Ord_2'])

df.head(10)

df = pd.get_dummies(df, prefix=['Ord_1'], columns=['Ord_1'])

df.head(10)

# OUPUT

1. data:

![Screenshot 2022-10-13 084706](https://user-images.githubusercontent.com/95408668/195491670-e55da592-76d4-49cc-b583-feab6a9ace9d.png)

![Screenshot 2022-10-13 084735](https://user-images.githubusercontent.com/95408668/195491744-bddd37ba-0887-4b33-8298-bb2e46af854c.png)

![Screenshot 2022-10-13 084809](https://user-images.githubusercontent.com/95408668/195491765-4295f72d-3dee-4450-ac94-7cdd04802032.png)

![Screenshot 2022-10-13 084848](https://user-images.githubusercontent.com/95408668/195491792-dceedc75-2e40-4894-97f9-c41de492d5ee.png)

![Screenshot 2022-10-13 084906](https://user-images.githubusercontent.com/95408668/195491845-eb6c62e4-96e7-40c6-a576-fe34c66cef61.png)

2. Encoding Dataset:

![image](https://user-images.githubusercontent.com/95408668/195492671-c4979511-89cb-415f-8c4c-d9ee99b4f916.png)

![image](https://user-images.githubusercontent.com/95408668/195492765-74affdca-c4eb-4920-b4db-76785afe5525.png)

![image](https://user-images.githubusercontent.com/95408668/195492856-391e6df7-20a3-42a9-aca4-3787582f34cf.png)

![image](https://user-images.githubusercontent.com/95408668/195492920-95fae5e3-1dc4-4b7b-b110-19a267ab014b.png)

3. Titanic dataset:

![image](https://user-images.githubusercontent.com/95408668/195495015-e8c9b7ec-bfd6-4c12-b0bb-c41c473df919.png)

![image](https://user-images.githubusercontent.com/95408668/195495055-578b6c55-59dd-48c6-83e5-1da1186c5534.png)

![image](https://user-images.githubusercontent.com/95408668/195495107-1c48a856-38de-4081-b42f-a5ead70dae8a.png)

![image](https://user-images.githubusercontent.com/95408668/195495251-1ace0d2a-a10f-4b34-872b-c02bbbb51605.png)

![image](https://user-images.githubusercontent.com/95408668/195495303-2fea21a2-9178-4e3b-a7d2-864c07d56688.png)

![image](https://user-images.githubusercontent.com/95408668/195495368-2f501031-eda9-4c26-be86-8ae99f99fe25.png)

![image](https://user-images.githubusercontent.com/95408668/195495422-f60679f5-4767-4731-81bc-142ea910bfd9.png)

