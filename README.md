# DataCleansing
This is the first in a series of projects. The purpose of the data cleaning project is to clean-up the ‘Credit Card Application’ dataset by removing missing and other out of place characters. Initial examination of the dataset shows that we have missing values to contend with. There are 67 missing values in the dataset.

The dataset comprises continuous and nominal attributes of small and large values. For reasons of privacy, the dataset was published with column labels A1 – A16 replacing the actual descriptive labels.


## Dataset
The dataset is found at: - https://archive.ics.uci.edu/ml/datasets/credit+approval 

Number of instances (observations) = 690

Number of attributes =15 (columns A1-A15)

There is one class attribute (column A16) 

307 (44.5%) of the classifier is “+” and 383 (55.5%) is “-“

The groupings of attribute labels by value types are as below - 

  *Nominal*:              A1, A4, A5, A6, A7, A9, A10, A12, A13
  
  *Continuous*:           A2, A3, A8
  
  *Continuous (Integer)*: A11, A14, A15
  
  *Class Attribute*:      A16


## Process

### Step 1

The original dataset was in .txt format and below is an abstract of it.

b,30.83,0,u,g,w,v,1.25,t,t,01,f,g,00202,0,+

a,58.67,4.46,u,g,q,h,3.04,t,t,06,f,g,00043,560,+

The .txt file was imported into excel using the ‘import from text’ Excel menu to obtain a .xls file which looks like the following:

A1 A2 A3 A4 A5 A6 A7 A8 A9 A10 A11 A12 A13 A14 A15 A16

B 30.83 0 u G w v 1.25 t t 1 F g 202 0 +

A 58.67 4.46 u G q h 3.04 t t 6 F g 43 560 +

### Step 2
To prepare the required environment using Python pandas and numpy libraries, we issue the following commands.

*import pandas as pd*

*import numpy as np*

### Step 3
Next, to detect the character and distribution of the missing values we use the following codes
