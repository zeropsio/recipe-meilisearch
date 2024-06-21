# Zerops x Meilisearch
Recipe for running Meilisearch in Zerops Linux container.

> [!WARNING]
> Use the import script as one-time action. Do not tigger new deploy pipelines once your Meilisearch is running. Containers are volatile and this would cause the data to be wiped. A native support for Meilisearch Zerops service with a persistent disk is coming.

## Import as service
```yaml
#yamlPreprocessor=on
services:
  - hostname: meilisearch
    type: go@1
    enableSubdomainAccess: true
    buildFromGit: https://github.com/zeropsio/recipe-meilisearch
    envSecrets:
      MEILI_MASTER_KEY: <@generateRandomString(<16>)>
```
