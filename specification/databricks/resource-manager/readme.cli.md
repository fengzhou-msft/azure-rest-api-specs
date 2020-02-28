## CLI

These settings apply only when `--cli` is specified on the command line.

``` yaml $(cli)
cli:
  namespace: azure.mgmt.databricks
  flatten-all: true
  cmd-override:
    "^.*databricks operation.*$": "-"
```

