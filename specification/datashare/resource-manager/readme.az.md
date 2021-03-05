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
      group: datashare consumer-invitation
    set:
      group: datashare consumer invitation
  - where:
      command: datashare consumer invitation list-invitation
    set:
      command: datashare consumer invitation list
  - where:
      command: datashare consumer invitation reject-invitation
    set:
      command: datashare consumer invitation reject
  - where:
      group: ^datashare data-set$
    set:
      group: datashare dataset
  - where:
      group: datashare data-set-mapping
    set:
      group: datashare consumer dataset-mapping
  - where:
      group: datashare share-subscription
    set:
      group: datashare consumer share-subscription
  - where:
      command: datashare consumer share-subscription cancel-synchronization
    set:
      command: datashare consumer share-subscription synchronization cancel
  - where:
      command: datashare consumer share-subscription list-synchronization
    set:
      command: datashare consumer share-subscription synchronization list
  - where:
      command: datashare consumer share-subscription list-synchronization-detail
    set:
      command: datashare consumer share-subscription synchronization list-detail
  - where:
      command: datashare consumer share-subscription synchronize
    set:
      command: datashare consumer share-subscription synchronization start
  - where:
      command: datashare consumer-source-data-set list
    set:
      command: datashare consumer share-subscription list-source-dataset
  - where:
      group: datashare trigger
    set:
      group: datashare consumer trigger

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
