# Zerops x Meilisearch
Recipe for running Meilisearch in Zerops Linux container.

> [!WARNING]
> Do not tigger new deploy pipelines once your Meilisearch is running.
> Containers are volatile and this would cause the data to be wiped.
> A native support for Meilisearch with persistent disk is coming.

## Import as service
```yaml
#yamlPreprocessor=on
services:
  - hostname: meilisearch
    type: ubuntu@22.04
    enableSubdomainAccess: true
    buildFromGit: https://github.com/zeropsio/recipe-meilisearch
    envSecrets:
      MEILI_MASTER_KEY: <@generateRandomString(<16>)>
```
