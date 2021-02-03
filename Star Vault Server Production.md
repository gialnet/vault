# Star Vault Server Production

Create config file

Create data folder
>mkdir data


Start server
>./vault server -config=config.hcl

```
>root@DESKTOP-IR8COQJ:/opt/vault# ./vault operator init

Unseal Key 1: 9haQNyZ6nfhZmZX/raHhKi5RTXP4bINxdBaV1sSN+rN1
Unseal Key 2: pQv5zKD0OqjYhYEvNYex3rAvCP7kuJbwM4Ste5YUZCZ9
Unseal Key 3: CHTnnIFKrCzF/2+oxCULIDph9mpW2HhGye7WtefD2nL2
Unseal Key 4: XAa+mB1njJFFapGEO49X0Aa/QWIeNi4/PuBNY+FPmehg
Unseal Key 5: omTJM7pXvUXZDGvTUgu92hKP+nuwgtUIgxgOAMIBuSnj

Initial Root Token: s.NRIwV8WeABmip4zXDRVStzmg

Vault initialized with 5 key shares and a key threshold of 3. Please securely
distribute the key shares printed above. When the Vault is re-sealed,
restarted, or stopped, you must supply at least 3 of these keys to unseal it
before it can start servicing requests.

Vault does not store the generated master key. Without at least 3 key to
reconstruct the master key, Vault will remain permanently sealed!

It is possible to generate new unseal keys, provided you have a quorum of
existing unseal keys shares. See "vault operator rekey" for more information.
```
