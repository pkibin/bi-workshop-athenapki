---
title: "Athena U2F + Smartcard"
chapter: true
weight: 6
---

## Athena U2F+Smartcard
A custom version of Feitian U2F token

1. Browser to <http://pdc.soho.com/admin>, login with pkiadmin / Password$1
1. Go to Manage -> Manage PKI Token, type in the user UPN, once found, if there is no “Status: User has Soft Token”, then click the “Issue Soft Token” button
1. You should see status: User has Soft Token
1. If you get any errors, STOP!! Use the ADUC, double check the user profile contains all valid fields, such as first & last name, email etc.
1. Do NOT insert Feitian U2F Token, double click and run c:\pki\U2FAdmin\U2FAdmin.exe
1. When prompted for a PIN:  test  Now you should be logged in.
1. Switch Program Token tab
1. Insert the U2F token, click the “Refresh” button, and type in UPN as shown.
1. Click the “Program Token” button, this may take up to 2 minutes, do NOT interrupt. Do not use the computer for anything!!! Until you see the PIN. Write down the 6 digit PIN
1. Optional: switch PIN Change tab, change PIN to something you can remember
1. Note: don’t program U2F token too often, it is not designed to be programmed/written many times.
