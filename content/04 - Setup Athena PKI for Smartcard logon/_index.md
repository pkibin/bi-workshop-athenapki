---
title: "Setup Athena PKI"
chapter: true
weight: 4
---

# Setup Athena PKI for Smartcard logon
1. Request a new DC cert from PKI
1. You need to login as a Domain Admin user to do the following steps:
1. You can get DC GUID by running cmd on DC server **$ repadmin /showreps pdc** ;
   pdc is the server name. to find the DSA object GUID, looks like this: a59f94d8-78ac-40f0-bb53-c666ce1d38dd
1. Install DC cert (P12 format) you just created, make sure you install the .p12 file, you will be asked for password, not the .cer file
   ![](/images/Aspose.Words.737acd22-b7f1-4581-ac73-da034e00b470.006.png)
1. To verifyDC cert: $ certutil -dcinfo verify
1. From Server Manager, Tools -> Group Policy Management; Current user should belong to **Domain Admin**
   ![](/images/Aspose.Words.737acd22-b7f1-4581-ac73-da034e00b470.007.png)
1. Add Trusted Root CA: C:\pki\data\sirc.crt
1. Add Intermediate CA: C:\pki\data\apca.crt & sitc.crt
   ![](/images/Aspose.Words.737acd22-b7f1-4581-ac73-da034e00b470.008.png)
1. From command line in admin mode, run this:
   C:\pki\data>**certutil -dspublish -f "apca.crt" NTAuthCA**
1. force update the GPO on member PC **$ gpupdate /force**
1. Use **Athena Smartcard Cert** template, issue a cert to user john
