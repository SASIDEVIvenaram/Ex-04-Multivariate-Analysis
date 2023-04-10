# Ex-04-Multivariate-Analysis
# AIM
To perform Multivariate EDA on the given data set.

# EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:

## STEP 1:
Import the built libraries required to perform EDA and outlier removal.
## STEP 2:
Read the given csv file
## STEP 3:
Convert the file into a dataframe and get information of the data.
## STEP 4:
Return the objects containing counts of unique values using (value_counts()).
## STEP 5:
Plot the counts in the form of Histogram or Bar Graph.
##STEP 6:
Use seaborn the bar graph comparison of data can be viewed.
## STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr()
## STEP 8:
Save the final data set into the file.


# PROGRAM:
Developed By: SASIDEVI V
Register No: 212222230136
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/SuperStore (2).csv")
df=pd.DataFrame(data)
df.head()
df.info()
df.describe()
df.isnull().sum()
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()

sns.scatterplot(x=df['Region'],y=df['Sales'])

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=states.index,y="Sales",data=states)

states=df.loc[:,["Ship Mode","Row ID"]]
states=states.groupby(by=["Ship Mode"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SHIP MODE")
plt.ylabel=("ROW ID")
plt.show()

sns.boxplot(x=df['Ship Date'],y=df['Sales'])
sns.displot(df, x="Region", hue="Category")
df.corr()
sns.heatmap(df.corr(),annot=True)
```


# OUTPUT:
## df.head()
![DS41](https://user-images.githubusercontent.com/118707332/230837789-284f3233-43e0-4fe3-9e2c-cc2cdd30bdb6.png)
## df.info()
![DS42](https://user-images.githubusercontent.com/118707332/230837799-d8443065-fb61-4f87-bfff-97812b76ff39.png)
## df.describe()
![DS43](https://user-images.githubusercontent.com/118707332/230837822-ed994831-7be2-4327-948a-4766fe221aeb.png)
## SUM OF NULL VALUES
![DS44](https://user-images.githubusercontent.com/118707332/230837833-877a6683-bc34-499f-9d5f-5b464fdf959f.png)
## AFTER REMOVING NULL VALUES
![DS45](https://user-images.githubusercontent.com/118707332/230837840-3ba42286-1df4-49ab-a4fd-8a5213dc4752.png)
## SCATTER PLOT
![DS46](https://user-images.githubusercontent.com/118707332/230837850-a3c5c6f6-44bf-4c62-82e5-16497567bebc.png)
## BAR PLOTS
![DS47](https://user-images.githubusercontent.com/118707332/230837858-89bb128d-51c7-4558-892e-8b0367ff0dd1.png)

![DS49](https://user-images.githubusercontent.com/118707332/230837981-f1d5e0fd-7086-4f15-ae57-fe42dfa5bd61.png)
## BOXPLOT
![DS410](https://user-images.githubusercontent.com/118707332/230837992-04464d49-8c01-4a07-abfc-45798f9d2d32.png)
## DIST PLOT
![DS411](https://user-images.githubusercontent.com/118707332/230837999-6716e3a4-b3e2-441d-8449-0960e8f22a79.png)
## CORRELATION COEFFICIENT INTERPRETATION
![DS412](https://user-images.githubusercontent.com/118707332/230838015-b51463b9-fc04-4b07-9ab7-f4cc1b3d2241.png)
## HEAT MAP
![DS413](https://user-images.githubusercontent.com/118707332/230838029-b7e68aeb-2405-46a1-95a9-376f3c5b6ba3.png)

# RESULT:
Thus we have read the given data and performed the multivariate analysis with different types of plots.



















