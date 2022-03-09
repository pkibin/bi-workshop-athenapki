---
title: "Use TPM virtual Smartcard"
chapter: true
weight: 7
---

## Use TPM virtual Smartcard (VSC)
If you don’t have a physical smartcard, you can find a machine with a TPM chip, (vmware fusion & workstation both support virtual TPM when used in UEFI mode)

1. Create a virtual smartcard, **pin length 8**
1. Cmd admin mode: $ tpmvscmgr.exe create /name "AthenaVSC" /AdminKey DEFAULT /PIN PROMPT /generate
1. Delete a virtual smarcard, cmd admin mode: $ tpmvscmgr.exe destroy /instance ROOT\SMARTCARDREADER\0000
1. Validate the new TPM VSC by: $ certutil -scinfo
1. Load cert to TPM VSC by: $ certutil -v -pin 00000000 -csp "Microsoft Base Smart Card Crypto Provider" -p test -importpfx John\_IAM\_Token[test].p12

You should now be able to login to Windows with a Smartcard or VSC.  Tested successfully on AD member hosts like Windows 8.1, Windows 10 or Domain Controller (Windows 2019) itself.

