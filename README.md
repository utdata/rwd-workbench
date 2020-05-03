# Notes about Data Workbench

Workbench is based on Python's [pandas](https://pandas.pydata.org/) module, which means you can leverage pandas to do things that Workbench can't do natively.

This is a collection of some of those things.

## How it works

- In Workbench, create a new step and choose the [Python](http://help.workbenchdata.com/en/articles/1484226-python-editor) module.
- Define a function called `process` that accepts the current data as `table` (which will be a `pd.DataFrame`) and return the same `table`. You can use the following packages:
  - math
  - pd ([Pandas](https://pandas.pydata.org/pandas-docs/stable/reference/index.html))
  - np ([numpy](https://docs.scipy.org/doc/numpy/reference/routines.html))

```python
def process(table):
    # Do your thing here
    return table
```

Your pandas dataframe object is called `table`, so you can reference columns as `table['columnname']` or `table.columnname`.

## Examples

- [Reshaping using Pandas melt](reshape-melt.md)
- [Using zfill to fix IDs that start with zero](zfill.md)
