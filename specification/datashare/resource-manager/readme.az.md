## AZ

These settings apply only when `--az` is specified on the command line.

``` yaml $(az)
az:
  extensions: datashare
  namespace: azure.mgmt.datashare
  package-name: azure-mgmt-datashare
az-output-folder: $(azure-cli-extension-folder)/src/datashare
python-sdk-output-folder: "$(az-output-folder)/azext_datashare/vendored_sdks/datashare"
  
directive:
  - where:
      group: ^datashare share$
    set:
      group: datashare
  - where:
      group: ^datashare data-set$
    set:
      group: datashare dataset
  - where:
      group: datashare trigger
    set:
      group: datashare consumer trigger
  - where:
      group: datashare share-subscription
    set:
      group: datashare consumer share-subscription
  - where:
      group: datashare data-set-mapping
    set:
      group: datashare consumer dataset-mapping
  - where:
      group: datashare consumer-invitation
    set:
      group: datashare consumer invitation
  - where:
      command: datashare consumer-source-data-set list
    set:
      command: datashare consumer share-susbcription list-source-dataset
  - where:
      command: datashare consumer share-subscription cancel-synchronization
    set:
      command: datashare consumer share-subscription synchronization cancel
  - where:
      command: ^datashare consumer share-subscription list-synchronization$
    set:
      command: datashare consumer share-subscription synchronization list
  - where:
      command: datashare consumer share-subscription list-synchronization-detail
    set:
      command: datashare consumer share-subscription synchronization list-detail

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
