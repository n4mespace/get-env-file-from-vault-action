Get env-file from Hashicorp Vault GitHub Action
-----------------------------------------------


Simple action to get env file from HashiCorp Vault™.

## Example Usage

```yaml
jobs:
  build:
    # ...
    steps:
      # ...
      - name: Get env file
        uses: n4mespace/get-env-file-from-vault-action@v1
        with:
          VAULT_ADDR: https://vault.mycompany.com:8200
          VAULT_USERNAME: ${{ secrets.VAULT_USERNAME }}
          VAULT_PASSWORD: ${{ secrets.VAULT_PASSWORD }}
          VAULT_SECRETS_PATH: ${{ secrets.VAULT_SECRETS_PATH }}
      # ...
```

will get all the secrets from `kv` storage from `VAULT_SECRETS_PATH` and put it in a `.env` 

## Authentication method

Currently, only `userpass` login method is implemented. `VAULT_USERNAME` and `VAULT_PASSWORD` to authenticate with Vault.

## Reference

Here are all the inputs available through `with`:

| Input                | Description                              | Default | Required |
|----------------------|------------------------------------------|---------|----------|
| `VAULT_ADDR`         | Vault url                                |         | ✔        |
| `VAULT_USERNAME`     | Vault login username for `userpass` auth |         | ✔        |
| `VAULT_PASSWORD`     | Vault login password for `userpass` auth |         | ✔        |
| `VAULT_SECRETS_PATH` | Vault secrets path                       |         | ✔        |
| `ENV_FILE_NAME`      | Name of created env-file                 | .env    |          |
