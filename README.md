# DataCleansing
This is the first in a series of projects. The purpose of the data cleaning project is to clean-up the ‘Credit Card Application’ dataset by removing missing and other out of place characters. Initial examination of the dataset shows that we have missing values to contend with. There are 67 missing values in the dataset.

The dataset comprises continuous and nominal attributes of small and large values. For reasons of privacy, the dataset was published with column labels A1 – A16 replacing the actual descriptive labels.


## Dataset
The dataset is found at: - https://archive.ics.uci.edu/ml/datasets/credit+approval 

**Number of instances (observations)**: 690

**Number of attributes**: 15 (columns A1-A15)

There is **one class attribute** (column A16) 

**Classifier Breakdown**: 307 (44.5%) =  “+” and 383 (55.5%) = “-“


The groupings of attribute labels by value types are as below - 

  **Nominal**:              A1, A4, A5, A6, A7, A9, A10, A12, A13
  
  **Continuous**:           A2, A3, A8
  
  **Continuous (Integer)**: A11, A14, A15
  
  **Class Attribute**:      A16


## Process

### Step 1

The original dataset was in .txt format and below is an abstract of it.

> b,30.83,0,u,g,w,v,1.25,t,t,01,f,g,00202,0,+

> a,58.67,4.46,u,g,q,h,3.04,t,t,06,f,g,00043,560,+

The .txt file was imported into excel using the ‘import from text’ Excel menu to obtain a .xls file which looks like the following:

| A1 | A2 | A3 | A4 | A5 | A6 | A7 | A8 | A9 | A10 | A11 | A12 | A13 | A14 | A15 | A16
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| B | 30.83 | 0 | u | G | w | v | 1.25 | t | t | 1 | F | g | 202 | 0 | + |
| A | 58.67 | 4.46 | u | G | q | h | 3.04 | t | t | 6 | F | g | 43 | 560 | + |


### Step 2
To prepare the required environment using Python pandas and numpy libraries, we issue the following commands.

> *import pandas as pd*

> *import numpy as np*

### Step 3
Next, to detect the character and distribution of the missing values we use the following codes:

> missing_values = ["?"]

> df=pd.read_csv('C:/Users/Owner/Desktop/DATA/CAD/ABC.csv', na_values=missing_values)

> df.isnull().sum()

The total number of missing values is derived using the following code:

> df.isnull().sum().sum()

**_Output_**: 67

To confirm whether or not the dataset was imported correctly, examine the first five (5) and the last five (5) records of the dataset:

> df.head(5)

**_Output_**:

A1 A2 A3 A4 A5 A6 A7 A8 A9 A10 A11 A12 A13 A14 A15 A16

0 b 30.83 0.000 u g w v 1.25 t t 1 f g 202 0 +

1 a 58.67 4.460 u g q h 3.04 t t 6 f g 43 560 +

2 a 24.5 0.500 u g q h 1.50 t f 0 f g 280 824 +

3 b 27.83 1.540 u g w v 3.75 t t 5 t g 100 3 +

4 b 20.17 5.625 u g w v 1.71 t f 0 f s 120 0 +

> df.tail(5)

**_Output_**:

A1 A2 A3 A4 A5 A6 A7 A8 A9 A10 A11 A12 A13 A14 A15 A16

685 b 21.08 10.085 y p e h 1.25 f f 0 f g 260 0 -

686 a 22.67 0.750 u g c v 2.00 f t 2 t g 200 394 -

687 a 25.25 13.500 y p ff ff 2.00 f t 1 t g 200 1 -

688 b 17.92 0.205 u g aa v 0.04 f f 0 f g 280 750 -

689 b 35 3.375 u g c h 8.29 f f 0 t g 0 0 -

Next, we confirm that the entire dataset is captured and to do this a glimpse at the basic statistics of numerical features is revealed through the following codes:

> df.shape

**_Output_**: (690, 16)

> df.describe()

INSERT OUTPUT 1 HERE

Furthermore, to detect unique values and counts for all variables using the code below: 
[We do this in order to determine inputs for nominal columns.]

df.apply(pd.Series.value_counts) 
