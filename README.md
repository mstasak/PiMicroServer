# PiMicroServer

## Intro
Setup instructions to make a web (Apache HTTP 2) + db (MariaDB) + SCM (Gitlab CE) + File (Samba) server using a Raspberry Pi 3B.

The objective here is to make a development server which will be available nearly 24/7 and provide essential development services like file server, relational db server, source control management, and web server.  High performance is not an objective, we are obviously trying to do much with a very small server.

I've configured my Pi with a USB3 SATA SDD (512MB) to improve on the performance, durability and capacity of a flash stick.


## Define the stack
### File Server
Using [SAMBA](SambaService.md), sharing one directory: /var/samba/shared/
### Web Server
Incomplete; will probably use [Apache](AppacheHTTPServer.md) HTTPD 2.x
### DB Server(s)
Using [MariaDB](MariaDBService.md), a MySQL fork
### SCM Server
Incomplete; will probably use [GitLab CE](GitLabService.md), over Apache HTTP 2.x?  I think some versions also work over NGINX?

## Implementation

## Possible Future Additions
### Container Service (Kubernetes/?)
### NoServer Service
### NoSQL Database (MongoDB/?)
### Wiki Host
### Blog Host
### Snippet Service
### Copy and paste service
### Dynamic Host Lookup
### Messaging / Mail
### Application Server (Tomcat/etc)
### Alternative RDBMSs (MySQL/PostgreSQL/Oracle (Express?)/SQL Server for Linux/)
### Wake on LAN functionality
### Encrypted access from internet
