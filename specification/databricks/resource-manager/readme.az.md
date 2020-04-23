## AZ

These settings apply only when `--az` is specified on the command line.

``` yaml $(az)
az:
  extensions: databricks
  namespace: azure.mgmt.databricks
  package-name: azure-mgmt-databricks
az-output-folder: $(azure-cli-extension-folder)/src/databricks
python-sdk-output-folder: "$(az-output-folder)/azext_databricks/vendored_sdks/databricks"
  
#cli:
#    cli-directive:
#      directive on operationGroup
#       - select: 'operationGroup'
#         where:
#             operationGroup: 'operations'
#         hidden: true
#       - where:
#             parameter: location
#         required: true

```
