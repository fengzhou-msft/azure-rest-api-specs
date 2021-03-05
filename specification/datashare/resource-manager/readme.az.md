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
  # - where:
  #     group: datashare consumer-invitation list-invitation
  #   set:
  #     group: datashare consumer invitation list
  # - where:
  #     group: datashare consumer-invitation reject-invitation
  #   set:
  #     group: datashare consumer invitation reject
  - where:
      group: datashare data-set
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
  # - where:
  #     group: datashare share-subscription cancel-synchronization
  #   set:
  #     group: datashare consumer share-subscription synchronization cancel
  # - where:
  #     group: datashare consumer-source-data-set list
  #   set:
  #     group: datashare consumer share-subscription list-source-dataset
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
