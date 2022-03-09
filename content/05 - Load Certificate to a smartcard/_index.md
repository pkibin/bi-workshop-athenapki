---
title: "Load Certificate"
chapter: true
weight: 5
---

# Load Certificate to a smartcard
**Note**: this is for lab testing purposes only, for production deployment, you need to use the Token Enrollment service instead.

* On a Windows 10 member PC, login as an admin user, create a file: p12-import.reg with the following info:
   Windows Registry Editor Version 5.00

[HKEY LOCAL MACHINE\SOFTWARE\Microsoft\Cryptography\Defaults\Provider\Microsoft Base Smart Card Crypto Provider]

"AllowPrivateExchangeKeyImport"=dword:000000001

[HKEY LOCAL MACHINE\SOFTWARE\Microsoft\Cryptography\Defaults\Provider\Microsoft Base Smart Card Crypto Provider]

"AllowPrivateSignatureKeyImport"=dword:000000001

* Apply1 the p12-import.reg
