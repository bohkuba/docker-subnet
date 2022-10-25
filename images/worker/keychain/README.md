###### Worker is responsible for building, packaging and deploying artifacts to the Docker Registry
  - Authorize it to work with docker by creating credentials file under images/worker/keychain/docker
    - Generate Docker Access Token
    - Create a ``` docker ``` file with credentials under images/worker/keychain/docker
    - File format is ``` registry_name:access_token ```
