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
  ![page_1](https://github.com/user-attachments/assets/c5cf12f3-034e-48f5-b583-4ec6b3ca98b9)
  ![page_2](https://github.com/user-attachments/assets/fc675b4d-19ea-49dc-aee4-b3803e271e30)
  ![page_3](https://github.com/user-attachments/assets/a18a954e-56a2-4cb2-bfae-8d222cde0faf)
  ![page_4](https://github.com/user-attachments/assets/530b2f52-e8b5-4a27-8393-aa546ceae905)
  ![page_5](https://github.com/user-attachments/assets/278c5d55-6b54-43f3-9f39-3771af4c8510)
  ![page_6](https://github.com/user-attachments/assets/108e4194-a52a-47b4-869e-364e321c29a4)
  ![page_7](https://github.com/user-attachments/assets/838ffad5-825c-4c70-8f9b-01f4deb6f1e4)
  ![page_8](https://github.com/user-attachments/assets/fd45025d-2d27-4bad-a248-46be10d97922)
# RESULT:
       The data was successfully read,feature encoding and transformation were performed.

       
