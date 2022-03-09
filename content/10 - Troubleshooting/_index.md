---
title: "Troubleshooting"
chapter: true
weight: 10
---

# Troubleshooting
## Smartcard logon error:
- An untrusted certification authority was detected while processing the smart card certificate used for authentication.
- An untrusted certification authority was detected while processing the smart card certificate used for authentication.
- The smart card certificate used for authentication was not trusted.
- Signing in with a smart card isn’t supported for your account. For more info, contact your administrator
- Smart card or certificate sign-in failed. Please contact your administrator and tell them that the KDC certificate couldn’t be validated. Additional information might be available in the system event log
- Insufficient system resources exist to complete the requested service.
   
This might be a driver issue. Win8 works fine, but win10 and win2019 have this error. When connected to the Internet, win10 login worked, same thing when disconnecting the network on Windows 10. Win10 login also works when disconnecting the windows2019 pdc. Win8 does not have this problem. Guess win2019 AD needs some sort of Internet connection.

## Event Viewer error:
- The client has failed to validate the domain controller certificate for pdc.soho.com. The following error was returned from the certificate validation process: The revocation function was unable to check revocation for the certificate.
- Event ID 19: This event indicates an attempt was made to use smartcard logon, but the KDC is unable to use the PKINIT protocol because it is missing a suitable certificate.
- Event ID 29: The Key Distribution Center (KDC) cannot find a suitable certificate to use for smart card logons, or the KDC certificate could not be verified. Smart card logon may not function correctly if this problem is not resolved. To correct this problem, either verify the existing KDC certificate using certutil.exe or enroll for a new KDC certificate.
  
*Event ID 19 & 29 often come in pairs, one possibility is the online CRL is not up to date, this happens if your lab AD was shut down for a long time, wait until TrustOne CA service refreshes it’s CRL publication, try login again.*

- EventID 11: The Distinguished Name in the subject field of your smart card logon certificate does not contain enough information to identify the appropriate domain on an non-domain joined computer. Contact your system administrator.
- The revocation function was unable to check revocation for the certificate.
  
*On the AD Member host, apply this reg hack to disable CRL checking: (reboot afterward)**
```
  Windows Registry Editor Version 5.00

[HKEY\_LOCAL\_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa\Kerberos\Parameters]

"UseCachedCRLOnlyAndIgnoreRevocationUnknownErrors"=dword:00000001

"CRLTimeoutPeriod"=dword:00000001
```

**On the Domain Controller, apply this reg hack to disable CRL checking**:
```
Windows Registry Editor Version 5.00

[HKEY\_LOCAL\_MACHINE\SYSTEM\CurrentControlSet\Services\kdc]

"UseCachedCRLOnlyAndIgnoreRevocationUnknownErrors"=dword:00000001

[HKEY\_LOCAL\_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa\Kerberos\Parameters]

"UseCachedCRLOnlyAndIgnoreRevocationUnknownErrors"=dword:00000001

[HKEY\_LOCAL\_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa\Kerberos\Parameters]

"CRLTimeoutPeriod"=dword:00000001
```
Run **$ certutil -viewstore -enterprise ntauth** to see if you see the Soho Identity CA, if not, run cmd in admin mode: $ **gpupdate /force**

- Use Windows Event Viewer, go to windows Logs->System, look for Error.
- Check DC cert: $ certutil -dcinfo verify
- Check DC: $ dcdiag /test:CheckSecurityError; or dcdiag /a
