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

