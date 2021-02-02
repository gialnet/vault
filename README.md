# vault
Notes about HashiCorp Vault

start server
>/opt/vault/vault server -dev

go to cmd line

Windows Powershell
>$env:VAULT_TOKEN="s.Frf8sSe2iw8iM8iH0SHuANTm"
$env:VAULT_ADDR="http://127.0.0.1:8200"

Linux

>export VAULT_TOKEN="s.Frf8sSe2iw8iM8iH0SHuANTm"

>export VAULT_ADDR="http://127.0.0.1:8200"


vault kv get kv/redmoon/servers