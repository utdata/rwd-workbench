Notes about Data Workbench

## Python modules

Here is an example of using zfill to affect a column.

```python
def process(table):
    table['ZIP'] = table['ZIP'].astype(str).str.zfill(5)
    return table
```