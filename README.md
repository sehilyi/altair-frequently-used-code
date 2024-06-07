# altair-frequently-used-code
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

Append custome data rows:
```py
d = d.append({'x': 0, 'y': None, 'lab': lab, 'siteid': 'META_GERMANY', 'day': 'day1', 'period': 'early'}, ignore_index=True)
```

Filter by null checking:
```py
pd.isnull(df.var2)
```

Filter by str contains:
```py
df[df['A'].str.contains("hello")]
```

Concat strings in two columns:
```py
df['siteid-phase'] = df.siteid + df.phase.astype(str)
```

Two columns to dict:
```py
pd.Series(df.Letter.values,index=df.Position).to_dict()
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

Axis offset:
```py
axis=alt.Axis(titleX=-40)
```

Bar offset:
```py
mark_bar(xOffset=-10)
```

Alternative error bars (`mark_errorbar`):
```py
mark_bar(
    size=1,
    color='black',
    xOffset=-10
).encoding(
    x=alt.X(...),
    y=alt.Y(...),
    y2=alt.Y(...),
)
```

Colors:
```py
color=alt.Color('symbol', scale=alt.Scale(scheme='category20')),
```

Filters:
```py
.transform_calculate(
    order="{'Low Risk':0, 'Medium Risk': 1, 'High Risk': 2}[datum.variable]"  
).transform_filter(
    {'field': 'metric', 'oneOf': [metric]}
)
```

Log scale:
```py
alt.Chart(df).transform_filter(
    alt.datum.foos > 0  
).mark_bar().encode(
    alt.X('foos', scale=alt.Scale(type='log')),
    y='group'
)
```

Use multi-line axis title:
```py
y=alt.Y('mean:Q', scale=alt.Scale(zero=False), title=['All Patients' if patient_group == 'all' else "Ever Severe Patients", 'Mean Lab Value'] if i == 0 else None, axis=alt.Axis(titleX=titleX)),
```

Dashed lines:
```py
alt.Chart(source).mark_line().encode(
    x='date',
    y='price',
    color='symbol',
    strokeDash='symbol',
)
```
