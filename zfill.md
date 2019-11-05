# Zfill values

You can't define a datatype for a column before import, so sometimes text fields like ZIP codes are imported as numbers and drop the leading zero, i.e., `02101` in Massachusets becomes `2101`.

This uses pandas' [zfill](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.str.zfill.html) to put zeros back at the beginning if they are missing.

```python
def process(table):
    table['ZIP'] = table['ZIP'].astype(str).str.zfill(5)
    return table
```

I've found this also useful with education data that uses school numbers that start with zero and Census bureau data with GEOid columns.