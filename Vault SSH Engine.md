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


>vault write ssh/sign/root public_key=@$HOME/.ssh/id_rsa.pub

```
PS C:\Windows\System32> vault write ssh/sign/root public_key=@$HOME/.ssh/id_rsa.pub
Key              Value
---              -----
serial_number    754c9e66550b562c
signed_key       ssh-rsa-cert-v01@openssh.com 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
```