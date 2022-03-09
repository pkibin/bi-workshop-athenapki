---
title: "Appendix"
chapter: true
weight: 11
---

# Appendix: certutil -dcinfo verify
C:\Users\pkiadmin>certutil -dcinfo verify
```
0: PDC

\*\*\* Testing DC[0]: PDC

\*\* Enterprise Root Certificates for DC PDC

No certificates in Enterprise Root store!

Enterprise Root store: Cannot find object or property. 0x80092004 (-2146885628 CRYPT\_E\_NOT\_FOUND)

\*\* KDC Certificates for DC PDC

Certificate 0:

Serial Number: 66

Issuer: CN=Athena PKI IAM CA, O=SoHo Identity, S=Massachusetts, C=US

` `NotBefore: 2/12/2022 2:01 PM

` `NotAfter: 3/23/2026 1:01 PM

Subject: E=support@bostonidentity.com, CN=pdc.soho.com, OU=Athena IAM, O=Boston Identity, S=Massachusetts, C=US

Certificate Template Name (Certificate Type): DomainController

Non-root Certificate

Template: DomainController

Cert Hash(sha1): abb750b3252671fce8aff6b4fb4e7b36631c3c40

dwFlags = CA\_VERIFY\_FLAGS\_NT\_AUTH (0x10)

dwFlags = CA\_VERIFY\_FLAGS\_CONSOLE\_TRACE (0x20000000)

dwFlags = CA\_VERIFY\_FLAGS\_DUMP\_CHAIN (0x40000000)

Application[0] = 1.3.6.1.5.5.7.3.1 Server Authentication

Application[1] = 1.3.6.1.5.5.7.3.2 Client Authentication

ChainFlags = CERT\_CHAIN\_REVOCATION\_CHECK\_CHAIN\_EXCLUDE\_ROOT (0x40000000)

HCCE\_LOCAL\_MACHINE

CERT\_CHAIN\_POLICY\_NT\_AUTH

-------- CERT\_CHAIN\_CONTEXT --------

ChainContext.dwInfoStatus = CERT\_TRUST\_HAS\_PREFERRED\_ISSUER (0x100)

ChainContext.dwRevocationFreshnessTime: 14 Hours, 53 Minutes, 28 Seconds

SimpleChain.dwInfoStatus = CERT\_TRUST\_HAS\_PREFERRED\_ISSUER (0x100)

SimpleChain.dwRevocationFreshnessTime: 14 Hours, 53 Minutes, 28 Seconds

CertContext[0][0]: dwInfoStatus=101 dwErrorStatus=0

`  `Issuer: CN=Athena PKI IAM CA, O=SoHo Identity, S=Massachusetts, C=US

`  `NotBefore: 2/12/2022 2:01 PM

`  `NotAfter: 3/23/2026 1:01 PM

`  `Subject: E=support@bostonidentity.com, CN=pdc.soho.com, OU=Athena IAM, O=Boston Identity, S=Massachusetts, C=US

`  `Serial: 66

`  `SubjectAltName: Other Name:DS Object Guid=04 10 a5 9f 94 d8 78 ac 40 f0 bb 53 c6 66 ce 1d 38 dd, DNS Name=pki.soho.com, DNS Name=pdc.soho.com

`  `Template: DomainController

`  `Cert: abb750b3252671fce8aff6b4fb4e7b36631c3c40

`  `Element.dwInfoStatus = CERT\_TRUST\_HAS\_EXACT\_MATCH\_ISSUER (0x1)

`  `Element.dwInfoStatus = CERT\_TRUST\_HAS\_PREFERRED\_ISSUER (0x100)

`    `CRL (null):

`    `Issuer: CN=Athena PKI IAM CA, O=SoHo Identity, S=Massachusetts, C=US

`    `ThisUpdate: 2/12/2022 9:59 PM

`    `NextUpdate: 2/16/2022 9:59 PM

`    `CRL: 0b9eb89c21465f5627cdff0fba31d98a606060a6

`  `Application[0] = 1.3.6.1.5.5.7.3.1 Server Authentication

`  `Application[1] = 1.3.6.1.5.5.7.3.2 Client Authentication

CertContext[0][1]: dwInfoStatus=101 dwErrorStatus=0

`  `Issuer: CN=SoHo Identity Root CA, O=SoHo Identity, L=New York, S=New York, C=US

`  `NotBefore: 1/1/2022 2:41 PM

`  `NotAfter: 1/1/2027 2:41 PM

`  `Subject: CN=Athena PKI IAM CA, O=SoHo Identity, S=Massachusetts, C=US

`  `Serial: 5556

`  `Cert: 5982c768deb5fd2cf3661bb39a8778630f04824a

`  `Element.dwInfoStatus = CERT\_TRUST\_HAS\_EXACT\_MATCH\_ISSUER (0x1)

`  `Element.dwInfoStatus = CERT\_TRUST\_HAS\_PREFERRED\_ISSUER (0x100)

`    `CRL (null):

`    `Issuer: CN=SoHo Identity Root CA, O=SoHo Identity, L=New York, S=New York, C=US

`    `ThisUpdate: 2/12/2022 9:59 PM

`    `NextUpdate: 2/16/2022 9:59 PM

`    `CRL: a4a01f5b53584e49a1219707697eeeda2f460c44

CertContext[0][2]: dwInfoStatus=109 dwErrorStatus=0

`  `Issuer: CN=SoHo Identity Root CA, O=SoHo Identity, L=New York, S=New York, C=US

`  `NotBefore: 8/8/2017 12:28 PM

`  `NotAfter: 8/8/2027 12:28 PM

`  `Subject: CN=SoHo Identity Root CA, O=SoHo Identity, L=New York, S=New York, C=US

`  `Serial: 1388

`  `Cert: 6e088f918a825ec373aeef60de9c820bd170cff4

`  `Element.dwInfoStatus = CERT\_TRUST\_HAS\_EXACT\_MATCH\_ISSUER (0x1)

`  `Element.dwInfoStatus = CERT\_TRUST\_IS\_SELF\_SIGNED (0x8)

`  `Element.dwInfoStatus = CERT\_TRUST\_HAS\_PREFERRED\_ISSUER (0x100)

Exclude leaf cert:

`  `Chain: 64e659c5c8cd3ba6bce91414fc953697cf860e43

Full chain:

`  `Chain: 299688000c5ab9b0bb34222bd93d7fd221678a30

\------------------------------------

Verified Issuance Policies: None

Verified Application Policies:

`    `1.3.6.1.5.5.7.3.1 Server Authentication

`    `1.3.6.1.5.5.7.3.2 Client Authentication

1 KDC certificates for PDC

CertUtil: -DCInfo command FAILED: 0x80092004 (-2146885628 CRYPT\_E\_NOT\_FOUND)

CertUtil: Cannot find object or property.
```

# APPENDIX:  $ dcdiag /a

C:\Windows\system32>dcdiag /a
```
Directory Server Diagnosis

Performing initial setup:

`   `Trying to find home server...

`   `Home Server = pdc

`   `\* Identified AD Forest.

`   `Done gathering initial info.

Doing initial required tests

`   `Testing server: Default-First-Site-Name\PDC

`      `Starting test: Connectivity

`         `......................... PDC passed test Connectivity

Doing primary tests

`   `Testing server: Default-First-Site-Name\PDC

`      `Starting test: Advertising

`         `......................... PDC passed test Advertising

`      `Starting test: FrsEvent

`         `......................... PDC passed test FrsEvent

`      `Starting test: DFSREvent

`         `There are warning or error events within the last 24 hours after the SYSVOL has been shared.  Failing SYSVOL replication problems may cause Group Policy problems.

`         `......................... PDC failed test DFSREvent

`      `Starting test: SysVolCheck

`         `......................... PDC passed test SysVolCheck

`      `Starting test: KccEvent

`         `......................... PDC passed test KccEvent

`      `Starting test: KnowsOfRoleHolders

`         `......................... PDC passed test KnowsOfRoleHolders

`      `Starting test: MachineAccount

`         `......................... PDC passed test MachineAccount

`      `Starting test: NCSecDesc

`         `......................... PDC passed test NCSecDesc

`      `Starting test: NetLogons

`         `......................... PDC passed test NetLogons

`      `Starting test: ObjectsReplicated

`         `......................... PDC passed test ObjectsReplicated

`      `Starting test: Replications

`         `......................... PDC passed test Replications

`      `Starting test: RidManager

`         `......................... PDC passed test RidManager

`      `Starting test: Services

`         `......................... PDC passed test Services

`      `Starting test: SystemLog

`         `An error event occurred.  EventID: 0x00002720

`            `Time Generated: 02/13/2022   12:52:14

`            `Event String: The application-specific permission settings do not grant Local Activation permission for the COM Server application with CLSID

`         `An error event occurred.  EventID: 0x00002720

`            `Time Generated: 02/13/2022   12:52:14

`            `Event String: The machine-default permission settings do not grant Local Activation permission for the COM Server application with CLSID

`         `An error event occurred.  EventID: 0x00002720

`            `Time Generated: 02/13/2022   12:52:14

`            `Event String: The application-specific permission settings do not grant Local Activation permission for the COM Server application with CLSID

`         `An error event occurred.  EventID: 0x00002720

`            `Time Generated: 02/13/2022   12:52:14

`            `Event String: The machine-default permission settings do not grant Local Activation permission for the COM Server application with CLSID

`         `......................... PDC failed test SystemLog

`      `Starting test: VerifyReferences

`         `......................... PDC passed test VerifyReferences


`   `Running partition tests on : ForestDnsZones

`      `Starting test: CheckSDRefDom

`         `......................... ForestDnsZones passed test CheckSDRefDom

`      `Starting test: CrossRefValidation

`         `......................... ForestDnsZones passed test CrossRefValidation

`   `Running partition tests on : DomainDnsZones

`      `Starting test: CheckSDRefDom

`         `......................... DomainDnsZones passed test CheckSDRefDom

`      `Starting test: CrossRefValidation

`         `......................... DomainDnsZones passed test CrossRefValidation

`   `Running partition tests on : Schema

`      `Starting test: CheckSDRefDom

`         `......................... Schema passed test CheckSDRefDom

`      `Starting test: CrossRefValidation

`         `......................... Schema passed test CrossRefValidation

`   `Running partition tests on : Configuration

`      `Starting test: CheckSDRefDom

`         `......................... Configuration passed test CheckSDRefDom

`      `Starting test: CrossRefValidation

`         `......................... Configuration passed test CrossRefValidation

`   `Running partition tests on : soho

`      `Starting test: CheckSDRefDom

`         `......................... soho passed test CheckSDRefDom

`      `Starting test: CrossRefValidation

`         `......................... soho passed test CrossRefValidation

`   `Running enterprise tests on : soho.com

`      `Starting test: LocatorCheck

`         `......................... soho.com passed test LocatorCheck

`      `Starting test: Intersite

`         `......................... soho.com passed test Intersite
```