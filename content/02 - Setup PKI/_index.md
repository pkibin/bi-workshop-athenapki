---
title: "Setup PKI"
chapter: true
weight: 2
---

# Setup PKI
1. Download and unzip [PKI all-in-one lab zip file](https://drive.google.com/file/d/1sqNRW5rxEyhZuto-ICjlrK08i0z6-IpF/view?usp=sharing) to c:\pki
1. Run mmc, File -> Add/Remove Snap-in, add "Certificates (Local Computer)"
1. Right click "Trusted Root Certification Auth" import c:\pki\data\sirc.crt
1. Right click "Intermediate Certification Auth" and import both c:\pki\data\apca.crt & sitc.crt
1. Save it to Console1.msc
1. Open command prompt in admin mode, run this:
   $ dism /online /enable-feature /all /featurename:IIS-ASPNET45
1. C:\pki\pki-webroot\website (Add IIS\_IUSRS, give default permission)
1. C:\pki\pki-webroot\webdata (Add IIS\_IUSRS, give Full control permission)
1. Search and run Internet Information Services (IIS) Manager
1. drill down to Sites -> Default Web Site, right click, Manage Website -> Advanced Settings ...  
   Change Physical Path to C:\pki\pki-webroot\website
1. Right click on "admin" node, click "Convert to Application", do the same for DTRAWS, otp, PKIAPI and tokenapi
1. Install c:\pki\tmp\vcredist\_x64[vs2013].exe
1. Open command prompt in admin mode
1. $ cd C:\pki\tmp; $ gacutil.exe /i System.Data.SQLite.dll
1. $ cd C:\pki\ca\svc; $ PKICAService.exe /i (This installs TrustOne CA Service)
1. Using "Administrative Tools" -> "Services", Find "TrueOne CA service", change Log On to "pkiadmin" user.
1. If the TrustOne CA service does not run, you need to delete and re-deploy the folder: C:\pki\data\ca. You may need to take permission by:  $ takeown /f c:\pki\data\ca /r
1. $ cd C:\pki\ra\svc; $svcra.exe /i (This installs TrustOne RA Service)
1. $ cd C:\pki\token\svc;
   $ c:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe .\FansoWinSvc.exe (this installs TokenEnrollment Service)
1. You should be able to browse: <http://localhost/>
1. Login <http://localhost/DTRAWS/> with username **cao**, password: **Password$1**
1. If you are having trouble logging in, and see System Error [xxxxxxxxx] has occurred,  this means IIS couldn’t write log. The simplest solution would be to grant everyone full permission to c:\pki folder. In the real world, your IIS webroot folder would have a totally different configuration to ensure it’s security.
1. You may want to set Recovery for all 3 installed services
   ![](/images/Aspose.Words.737acd22-b7f1-4581-ac73-da034e00b470.001.png)
