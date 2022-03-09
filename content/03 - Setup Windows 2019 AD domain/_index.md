---
title: "Setup AD domain"
chapter: true
weight: 3
---
# Setup Windows 2019 AD domain
1. Install Windows 2019 with Desktop Experience edition
1. Setup static IP; Domain Controller (DC) needs to use static IP (ie. 10.7.7.7 / 255.255.255.0)
1. Change Computer name to: **pdc**
1. From Server Manager -> Add roles and features; Enable Active Directory Domain Services, DHCP (optional), DNS, IIS
   For the lab, DHCP is optional if you already have a DHCP service, or just use static IP.
1. Configure DHCP, add a scope. new IP address range![](/images/Aspose.Words.737acd22-b7f1-4581-ac73-da034e00b470.002.png)
1. Promote to AD Domain Controller (DC), Add a new forest, Set AD root domain name as “**soho.com**”
1. Set NetBIOS domain name: “**SOHO**”
1. You can safely ignore this warning: A delegation for this DNS server cannot be created because the authoritative parent zone cannot be found or it does not run Windows DNS server…
1. Use Admin Console, run $ dcdiag /a, make sure you don’t have errors, see appendix below.
1. Optional: Make sure you authorize the DHCP service with AD
   ![](/images/Aspose.Words.737acd22-b7f1-4581-ac73-da034e00b470.003.png)

1. Use ADUC, create a test account user, say “john”, make sure it has all required fields highlighted below:![](/images/Aspose.Words.737acd22-b7f1-4581-ac73-da034e00b470.004.png)
1. Optional: Install Windows 10, test join the domain, login with [**john@soho.com**](mailto:john@soho.com)
1. Optional: Install Windows 8.1U, test join the domain, login with [**john@soho.com**](mailto:john@soho.com)
1. Optional: by default pdc does not allow domain users to login locally. To add access, Go: Server Manager -> Group Policy Management; browse to Domain -> Domain Controllers; right click on Default Domain Controllers, select Edit … add user name or group into both Allow log on locally and Allow log on through Remote Desktop Service
   ![](/images/Aspose.Words.737acd22-b7f1-4581-ac73-da034e00b470.005.png)
