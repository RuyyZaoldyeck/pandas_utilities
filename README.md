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
```
