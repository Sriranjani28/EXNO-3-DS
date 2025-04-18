## EXNO-3-DS

# AIM:
To read the given data and perform Feature Encoding and Transformation process and save the data to a file.

# ALGORITHM:
STEP 1:Read the given Data.
STEP 2:Clean the Data Set using Data Cleaning Process.
STEP 3:Apply Feature Encoding for the feature in the data set.
STEP 4:Apply Feature Transformation for the feature in the data set.
STEP 5:Save the data to the file.

# FEATURE ENCODING:
1. Ordinal Encoding
An ordinal encoding involves mapping each unique label to an integer value. This type of encoding is really only appropriate if there is a known relationship between the categories. This relationship does exist for some of the variables in our dataset, and ideally, this should be harnessed when preparing the data.
2. Label Encoding
Label encoding is a simple and straight forward approach. This converts each value in a categorical column into a numerical value. Each value in a categorical column is called Label.
3. Binary Encoding
Binary encoding converts a category into binary digits. Each binary digit creates one feature column. If there are n unique categories, then binary encoding results in the only log(base 2)ⁿ features.
4. One Hot Encoding
We use this categorical data encoding technique when the features are nominal(do not have any order). In one hot encoding, for each level of a categorical feature, we create a new variable. Each category is mapped with a binary variable containing either 0 or 1. Here, 0 represents the absence, and 1 represents the presence of that category.

# Methods Used for Data Transformation:
  # 1. FUNCTION TRANSFORMATION
• Log Transformation
• Reciprocal Transformation
• Square Root Transformation
• Square Transformation
  # 2. POWER TRANSFORMATION
• Boxcox method
• Yeojohnson method

# CODING AND OUTPUT:

import pandas as pd

df=pd.read_csv("/content/Encoding Data (2).csv")

df

<img width="366" alt="SS 01" src="https://github.com/user-attachments/assets/fb72f06a-dbd3-4526-a49c-6134b9016227" />

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder

pm=['Hot','Warm','Cold']

e1=OrdinalEncoder(categories=[pm])

e1.fit_transform(df[["ord_2"]])

<img width="230" alt="SS 02" src="https://github.com/user-attachments/assets/8e2b2068-83d0-4cb9-9217-ee2096bea338" />

le=LabelEncoder()

dfc=df.copy()

dfc['ord_2']=le.fit_transform(dfc['ord_2'])

dfc

<img width="321" alt="SS 03" src="https://github.com/user-attachments/assets/b3841f36-c390-4dd6-8bef-07da803def8e" />

from sklearn.preprocessing import OneHotEncoder

ohe=OneHotEncoder(sparse_output=False)

df2=df.copy()

enc=pd.DataFrame(ohe.fit_transform(df2[['nom_0']]))

df2=pd.concat([df2,enc],axis=1)

pd.get_dummies(df2,columns=["nom_0"])

<img width="589" alt="SS 04" src="https://github.com/user-attachments/assets/ea16f664-0be6-46c7-afd9-604cd2e02ea0" />

pip install --upgrade category_encoders

<img width="916" alt="SS 05" src="https://github.com/user-attachments/assets/f2854e8d-c15b-4478-bea7-35ad1af10d59" />

from category_encoders import BinaryEncoder

df=pd.read_csv("/content/data (2).csv")

df

<img width="484" alt="SS 06" src="https://github.com/user-attachments/assets/4bcac7f6-0bb1-468a-90e0-a6637626b4af" />

be=BinaryEncoder()

nd=be.fit_transform(df['Ord_2'])

dfb=pd.concat([df,nd],axis=1)

dfb1=df.copy()

dfb

<img width="617" alt="SS 07" src="https://github.com/user-attachments/assets/6f5884ed-a620-49d4-a46e-60af558a530c" />

from category_encoders import TargetEncoder

te=TargetEncoder()

cc=df.copy()

new=te.fit_transform(X=cc["City"],y=cc["Target"])

cc=pd.concat([cc,new],axis=1)

cc

<img width="533" alt="SS 08" src="https://github.com/user-attachments/assets/5647b8cd-58c8-4e06-a270-8d3602f8d822" />

import pandas as pd

from scipy import stats

import numpy as np

df=pd.read_csv("/content/Data_to_Transform (1).csv")

df

<img width="860" alt="SS 09" src="https://github.com/user-attachments/assets/fe971c08-4a8e-447d-a7a8-efa829dad697" />

df.skew()

<img width="319" alt="SS 10" src="https://github.com/user-attachments/assets/d66537fb-df59-447e-ac4c-ed0d7b68c708" />

np.log(df["Highly Positive Skew"])

<img width="262" alt="SS 11" src="https://github.com/user-attachments/assets/a31d38d4-6bef-4a8c-bb82-207388fba294" />

np.reciprocal(df["Moderate Positive Skew"])

<img width="325" alt="SS 12" src="https://github.com/user-attachments/assets/9f452f96-164b-403d-b363-e59de0f5eb2a" />

np.sqrt(df["Highly Positive Skew"])

<img width="326" alt="SS 13" src="https://github.com/user-attachments/assets/c57801f8-f09e-4cfb-9c4b-1e4644d0b8cb" />

np.square(df["Highly Positive Skew"])

<img width="393" alt="SS 14" src="https://github.com/user-attachments/assets/24aff7e2-9b5c-4cce-8c6d-5483a2847b48" />

df["Highly Positive Skew_boxcox"],parameters=stats.boxcox(df["Highly Positive Skew"])

df

<img width="893" alt="SS 15" src="https://github.com/user-attachments/assets/e92ff0b2-90b4-40af-9fc3-5e4faa31f039" />

df["Moderate Negative Skew_yeojohnson"],parameters=stats.yeojohnson(df["Moderate Negative Skew"])

df.skew()

<img width="480" alt="SS 16" src="https://github.com/user-attachments/assets/71913685-702f-42f5-a8b1-76874c8a0479" />

df["Highly Negative Skew_yeojohnson"],parameters=stats.yeojohnson(df["Highly Negative Skew"])

df.skew()

<img width="384" alt="SS 17" src="https://github.com/user-attachments/assets/00670b89-bee7-4095-be30-87521cf2b04c" />

from sklearn.preprocessing import QuantileTransformer

qt=QuantileTransformer(output_distribution='normal')

df["Moderate Negative Skew_1"]=qt.fit_transform(df[["Moderate Negative Skew"]])

df

<img width="928" alt="SS 18" src="https://github.com/user-attachments/assets/6cc04968-a70b-4ae8-ad38-31830e509c26" />

import seaborn as sns

import statsmodels.api as sm

import matplotlib.pyplot as plt

sm.qqplot(df["Moderate Negative Skew"],line='45')

plt.show()

<img width="623" alt="SS 19" src="https://github.com/user-attachments/assets/714171a4-a130-4ce8-82df-35878c7f3a66" />

sm.qqplot(np.reciprocal(df["Moderate Negative Skew"]),line='45')

plt.show()

<img width="614" alt="SS 20" src="https://github.com/user-attachments/assets/173e4512-945c-4f17-a676-e0c4c0380171" />

from sklearn.preprocessing import QuantileTransformer

qt=QuantileTransformer(output_distribution='normal',n_quantiles=891)

df["Moderate Negative Skew"]=qt.fit_transform(df[["Moderate Negative Skew"]])

sm.qqplot(df["Moderate Negative Skew"],line='45')

plt.show()

<img width="656" alt="SS 21" src="https://github.com/user-attachments/assets/c19c9d71-d4fc-459e-bc52-4089c0663b21" />

df["Highly Negative Skew_1"]=qt.fit_transform(df[["Highly Negative Skew"]])

sm.qqplot(df['Highly Negative Skew'],line='45')

plt.show()

<img width="655" alt="SS 22" src="https://github.com/user-attachments/assets/181152a9-abe5-4e6e-a0f2-4685749fa012" />

sm.qqplot(df['Highly Negative Skew_1'],line='45')

plt.show()

<img width="702" alt="SS 23" src="https://github.com/user-attachments/assets/1b7ecfc7-3446-4dde-a17d-44f16cd6293e" />

dt=pd.read_csv("/content/titanic_dataset (2).csv")

from sklearn.preprocessing import QuantileTransformer

qt=QuantileTransformer(output_distribution='normal',n_quantiles=891)

dt["Age_1"]=qt.fit_transform(dt[["Age"]])

sm.qqplot(dt['Age'],line='45')

plt.show()

<img width="631" alt="SS 24" src="https://github.com/user-attachments/assets/b9ad4e84-0c81-4983-bc3a-6e8b25df8d88" />

sm.qqplot(dt['Age_1'],line='45')

plt.show()

<img width="662" alt="SS 25" src="https://github.com/user-attachments/assets/f2ad5bfd-36b4-4bf2-aefa-282b24787498" />

# RESULT:
       The data was successfully read,feature encoding and transformation were performed.

       
