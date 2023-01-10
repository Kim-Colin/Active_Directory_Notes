# Active_Directory_Notes

A scalable solution for security and permissions administration (only on windows server)

user accounts ((domain)/people or users using machine)

computer accounts ((LOCAL)/ accounts added to the domain as members)

schema is backend database for how/what info is stored about ojects and attr. containedc in direcotry.

Typically good security practice to separate domain and local users

Domain iscomprised of all computers and servers on network

domain controllers contrall all objs in domain (multiple (cluster) are used for redundancy and reliability)

DNS is used to mpa domains to ips

typically one domain controller (generally read only) per geographic location

Primary domain controller has user accounts and that forest can map to other domain controllers.

domain admin is basically the root user for the net.

subdomains creates a two-way, implicit, transitive trust (trust other subdomains on same level)

subdomains are added to origin domain (tree)
multiple domains/trees (forest)

groups manage sec on accs through inheritance of group policies

org units are groups ofr administration of accounts

group policies are permissions/restrictions for group of users

----------------------------------------------------
LAB

Domain Controller Instructions 

 

Custom Install 

Password: Admin123 

Local tab - click computer name 

Click change - change to memorable name 

Restart 

 

Click Manage 

Add role and services 

Active Directory Domain Services 

DHCP server 

DNS server 

IIS Server 

Once installed: 

Click flag and promote to domain controller 

Add a new forest 

Give domain a name (stygian.com) ****must have a .whatever*** 

Leave NetBIOS domain name - can’t be over 15 characters - from the old days 

Some admins think you should separate DB, log, SYSVOL on different partitions 

 

Control panel 

Network and internet  

Internet IPV4 properties 

Ip + Preferred DNS: 192.168.1.2 

Default gateway secondary DNS: 192.168.1.1 

Close 

Tools - DHCP 

Right click ipv4  - new scope 

Give name Basic 

Give 100 ips on same subnet 

Leave rest 

Give proper default gateway 

Tools - DNS 

Go to Forward Look-up zones 

Click Stygian.com then click server’s name 

Right click Stygian.com then click New Host 

Add name Printer 

Give ip 192.168.1.50 

Ping printer  - see how name resolves to an IP 

 

Adding a machine to a Domain 

Create a machine 

Password: Admin1234 

Control Panel - System Security - System 

*****Back to Server***** 

Tools - Active Directory Users and Computers 

Expand your domain 

Click Computers 

*****Back to Machine***** 

Click Change settings 

Click Network ID 

Join to domain 

Add username + password + Domain name computer is joining 

Administrator	+   Admin123 + Stygian.com 

Add name of machine/user + domain 

User1 + stygian.com 

Add name of admin account from earlier 

Give Administrator level access 

restart 

******Back to Domain Controller****** 

Click users in users and computers 

Right click users -> new -> User 

Make testuser@stygian.com 

Password Damin123 

Adding Groups 

Back to users and computers 

Right click new group 

Give name keep global 

Double click group 

Click members then add 

GPOs 

Tools -> Group Policy Management 

Right click Domains->stygian.com and add new OU 

Right click Group Policy Object and make new GPO 

Right click and edit GPO 

Open user Config - Policies - Windows Settings 

Administrative Settings - All Settings 

Set homepage to custom server home page 

Remove Task manager 

Disable Control Panel 

Lock taskbar + toolbars 

Click on your new testGPO and Add desired group/users to the security filtering 

 

Right Click TestOU 

Link an existing GPO 

Test GPO 

Tools -> users and computers 

Refresh 

Click Users  

Right click + move on desired user 

Move to TestOU 

***** BACK TO MACHINE ***** 

Logoff and logon 

 

 

-----------------------BREAKING INTO ACTIVE DIRECTORY ------------------------- 

 

Responder 

Bloodhound  

Mimikatz 

 

Scan for both PC’s on the network: nmap -A -T4 -vvv 192.168.1.0-254 

 

Run Responder to intercept network communication: responder -I eth0 -wF 

This will intercept wpad for internet proxy requests as well 

Gets username, domain, and pass 
