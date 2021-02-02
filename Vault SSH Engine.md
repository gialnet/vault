# Vault SSH Engine

vault write ssh/config/ca generate_signing_key=true

>PS C:\Windows\System32> vault write ssh/config/ca generate_signing_key=true
```
Key           Value
---           -----
public_key    ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDPhjBIJ0QQY0S1IklG8uqbwwejtOFLT1tg3I1+r+NN2HVJBzkt06N73kIwm8z0KAnlRmBhCkAyAkafAdHNCRHvyTVT45901nTx4e/YsZHVflP7RqsyK7dB5oNG/gwcwyyX4ElsB1QoBk0LawWq9mW/liWJnE8x4wFwnykvi02helyhgNQdTY2PwWpWadeS4heo6jGbA4J+ajri6NvNa3Ldw0PCdJHmYON0sbfFTc1gu1FqRVp3vIXbHUq+stL1jjF/uAzi/C8ic5rGmkggvFe3pSOpwLvIutO8bbdaHIgIQSvR+tEzRbop5q5PbWHETA6ubI/BKVOtSzDwCdGr76oqqPDFnXwGCa9eB91/RZBPoBHW/BKQTFR46nuyZIquI1DvbtkTXaXxsZtwgAFR6FdUqyY274pJlkmi8nQW01j3gAiJZXJAHDLfGY0/DlwQkZFGFPQm7SdcbOyJfG8B1z+fiJKHPOUU5Ib9b9FXHubXCJiziwIP92XpVTYKt/ehFUOAMtsCvkt/4hSAZ5qPfO4/IJ9UUCoXGVZbLy7mRYb/9C2jKcpcmaoHHZktf1PTVEo3E3WjJo+WGQ9vcIRrpMlUyMaMKBewQLZuPupbbeoVJjpxPQcXqfDOk3gomjkiTkmN9hcS2r3m6VZdnrNS7pmuZgumwY7I3PrrG+J1VDzIGw==
```

# Copy public key to file system

> curl -o /etc/ssh/trusted-user-ca-keys.pem http://127.0.0.1:8200/v1/ssh/public_key