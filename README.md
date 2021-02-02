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


>PS C:\Windows\System32> vault kv get secret/gialnet/services

```====== Metadata ======
Key              Value
---              -----
created_time     2021-02-02T15:02:47.4430821Z
deletion_time    n/a
destroyed        false
version          1

====== Data ======
Key         Value
---         -----
password    12345
user        gael
```