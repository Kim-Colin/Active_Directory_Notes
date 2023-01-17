# Securing Active Directory

https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/best-practices-for-securing-active-directory

Avenues of Compromise:

- Outdated Patching (WSUS - Windows Server Update Services): lots of ransomware automate and target this
- Outdated Software (i.e. adobe/chrome/firefox/etc.)
- Misconfigurations (Accounts, Admin, File r/w)
- Insecure Programming
- Profitable accounts: priv accounts, VIP accounts
- Physical Security: Not separating admin creds

## Reducing Attack Surface

Privileges: Built-in prv accounts and groups:

Regular users who in domain who have read accs

Enterprise admins = forest wide changes
domain admins = all powerful
admins = no priv on member servers or on workstations
schem admins = exist in forest root domain

https://stygiansecurity.com/introduction-to-kerberos/
https://learn.microsoft.com/en-us/windows-server/administration/server-core/server-core-roles-and-services

Defensive Techniques

- Auditing i.e. event logs (application, security, system, customlog)
- Baselining
- System Hardening
- Detection Methods
