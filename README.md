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

>PS C:\Windows\System32> vault status

```Key             Value
---             -----
Seal Type       shamir
Initialized     true
Sealed          false
Total Shares    1
Threshold       1
Version         1.6.1
Storage Type    inmem
Cluster Name    vault-cluster-23089317
Cluster ID      d6ec1504-eabe-d982-2da3-45b7309210bd
HA Enabled      false
```

>PS C:\Windows\System32> vault secrets list
```
Path          Type         Accessor              Description
----          ----         --------              -----------
cubbyhole/    cubbyhole    cubbyhole_9b9af7e7    per-token private secret storage
identity/     identity     identity_7c33f996     identity store
secret/       kv           kv_daa4549e           key/value secret storage
sys/          system       system_10046bb5       system endpoints used for control, policy and debugging
```

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