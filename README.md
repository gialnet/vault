# vault
Notes about HashiCorp Vault

start server
>/opt/vault/vault server -dev

go to cmd line

Windows Powershell
>$env:VAULT_TOKEN="s.NRIwV8WeABmip4zXDRVStzmg"
$env:VAULT_ADDR="http://127.0.0.1:8200"

Linux

>export VAULT_TOKEN="s.NRIwV8WeABmip4zXDRVStzmg"

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

Utility for extend Vault command line

Vaku https://github.com/lingrino/vaku


>root@DESKTOP-IR8COQJ:~# vaku folder list secret/gialnet

services

>root@DESKTOP-IR8COQJ:~# vaku folder read secret/gialnet

```
services
    password: 12345
    user: gael
```

>root@DESKTOP-IR8COQJ:~# vaku folder read secret/gialnet --format json

```
{
    "services": {
        "password": "12345",
        "user": "gael"
    }
}
```

>root@DESKTOP-IR8COQJ:~# vaku folder -h

```
Commands that act on Vault folders

Commands under the folder subcommand act on Vault folders. Folders
are designated by paths that end in a '/' such as 'secret/foo/'. Vaku
can list, copy, move, search, etc.. on Vault folders.

Usage:
  vaku folder [command]

Examples:
vaku folder list secret/foo

Available Commands:
  copy        Recursively copy all secrets in source folder to destination folder
  delete      Recursively delete all secrets in a folder
  delete-meta Recursively delete all secrets metadata and versions in a folder. V2 engines only.
  list        Recursively list all paths in a folder
  move        Recursively move all secrets in source folder to destination folder
  read        Recursively read all secrets in a folder
  search      Recursively search all secrets in a folder for a search string

Flags:
  -p, --absolute-path                  show absolute path in output
  -a, --address string                 address of the Vault server
      --destination-address string     address of the destination Vault server
      --destination-namespace string   name of the vault namespace to use in the destination client
      --destination-token string       token for the destination vault server (alias for --token)
  -h, --help                           help for folder
  -n, --namespace string               name of the vault namespace to use in the source client
      --source-address string          address of the source Vault server (alias for --address)
      --source-namespace string        name of the vault namespace to use in the source client (alias for --namespace)
      --source-token string            token for the source vault server (alias for --token)
  -t, --token string                   token for the vault server
  -w, --workers int                    number of concurrent workers (default 10)

Global Flags:
      --format string        output format: text|json (default "text")
  -i, --indent-char string   string used for indents (default "    ")
  -s, --sort                 sort output text (default true)

Use "vaku folder [command] --help" for more information about a command.
```
# Copy folder

>vaku folder copy secret/gialnet kv/redmoon

>root@DESKTOP-IR8COQJ:~# vaku folder list kv/redmoon --format json
```
[
    "services",
    "servers"
]
```
