# Enable GITHUB engine 

vault write auth/github/config organization=Vivaldi-Spring

vault write auth/github/map/users/gialnet value=default

>PS C:\Users\antonio> vault login -method=github token="d0f09..."

```
WARNING! The VAULT_TOKEN environment variable is set! This takes precedence
over the value set by this command. To use the value set by this command,
unset the VAULT_TOKEN environment variable or set it to the token displayed
below.

Success! You are now authenticated. The token information displayed below
is already stored in the token helper. You do NOT need to run "vault login"
again. Future Vault requests will automatically use this token.

Key                    Value
---                    -----
token                  s.9itCJaTWuvMbT3pcOgCkJiq6
token_accessor         zadFh8KtvToXhrWLYOu6jtsg
token_duration         768h
token_renewable        true
token_policies         ["default"]
identity_policies      []
policies               ["default"]
token_meta_org         Vivaldi-Spring
token_meta_username    gialnet
```
