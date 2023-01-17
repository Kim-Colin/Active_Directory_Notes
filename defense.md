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


##Lab
Tasks: 

 

Create OUs for four departments: 

Marketing 

HR 

Engineering 

Sales 

Add 2 Users to each 

Add a NOC_OPERATOR user as a Domain admin 

Enable SeImpersonatePrivilege 

Add a Substitute_NOC_OPERATOR as a standard user in Engineering 

Enable SeImpersonatePrivilege 

Enable RDP for NOC_OPERATOR and Substitute_NOC_OPERATOR 

 

Create a configuration baseline for users using the configuration manager 
