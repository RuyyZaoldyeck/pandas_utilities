# pandas_utilities
Utility functions or code snippets for data manipulation

```
import pandas as pd

missing_value_formats = ["n.a.","?","NA","n/a", "na", "--"]
df = pd.read_csv("employees.csv", na_values = missing_value_formats)

def make_int(i):
    try:
        return int(i)
    except:
        return pd.np.nan
        
print(df.isnull().values.any())
print(df.isnull().sum())

# drop all rows with NaN values
df.dropna(axis=0,inplace=True)


# drop all rows with atleast one NaN
new_df = df.dropna(axis = 0, how ='any')  

# drop all rows with all NaN
new_df = df.dropna(axis = 0, how ='all')


df['Salary'] = df['Salary'].map(make_int)
```
In order to fill missing values in a datasets, Pandas library provides us with fillna(), replace() and interpolate() functions
```
df['Salary'].fillna(0, inplace=True)
df['Gender'].fillna('No Gender', inplace=True)
df['Salary'].replace(to_replace = np.nan, value = 0,inplace=True)

#Methods references: https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.interpolate.html
df['Salary'].interpolate(method='linear', direction = 'forward', inplace=True) 

#use method = 'pad’ for taking values from the previous row.
df['Salary'].fillna(method='pad', inplace=True)

#use method = 'bfill’ for taking values from the next row.
df['Salary'].fillna(method='bfill', inplace=True)
```
