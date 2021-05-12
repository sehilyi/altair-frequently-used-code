# 4ce-frequently-used-codes
This repository contains python codes that I have been using frequently for 4CE projects. The purpose of this repository is for my convenience :)

## Pandas

Long to wide:
```py
df = pd.melt(df, id_vars=['siteid', 'lab', 'period', 'length'], value_vars=days, var_name='day', value_name='value')
```

Sort by value:
```py
df = df.sort_values(by=['siteid'])
```

Append vertical:
```py
meta.append(nometa)
```

## Altair

Channel:
```py
alt.X("day:Q", title=None, bin=alt.Bin(maxbins=20), axis=alt.Axis(labelAngle=0, tickCount=3), scale=alt.Scale(clamp=True)),
```

Text:
```py
text = points.mark_text(
    align='left',
    baseline='middle',
    dx=7
).encode(
    text='label'
)
```
