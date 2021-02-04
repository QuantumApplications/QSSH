# QSSH
This script is designed to make setting up and managing reverse proxy connections easy.
Example: You want to connect to a remote Raspberry Pi which doesn't have a static IP Address or has Port 22 blocked.

## You will need: 
A proxy server running Linux with a static IP or a domain (can be dynamic).
## How To: Target Server Setup (eg. Raspberry Pi)
1. Download script `$ wget https://raw.githubusercontent.com/QuantumApplications/QSSH/master/qssh`
1. Add exec perms `$ chmod +x qssh`
1. Register proxy server `$ ./qssh register <user>@<proxy>`
## How To: Connect to Target via Proxy (On your machine)
1. Download script `$ wget https://raw.githubusercontent.com/QuantumApplications/QSSH/master/qssh`
1. Add exec perms `$ chmod +x qssh`
1. Save credentials for the proxy `$ ssh-copy-id <user>@<proxy>`
1. Register proxy `$ ./qssh addProxy <user>@<proxy>`
1. Connect to target `$ ssh <target_hostname>`
## Moar features
* List available servers `$ ./qssh`
* Forward ports from the Proxy to target: `$ ./qssh register <user>@<proxy> -L 8086` \
This can be used for stuff like accessing a database on the proxy server.
* The register and addProxy commands can be used multiple times to update the list ov available targets or change the configuration.
