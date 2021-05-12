# 4ce-frequently-used-codes
This repository contains python codes that I have been using frequently for 4CE projects. The purpose of this repository is for my convenience :)

## The Code

Long to wide:
```py
df = pd.melt(df, id_vars=['siteid', 'lab', 'period', 'length'], value_vars=days, var_name='day', value_name='value')
```

Sort by value:
```py
df = df.sort_values(by=['siteid'])
```
