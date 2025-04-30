# NFSync
# Web Application Hosting using Apache, HTTPD, and NFS

This project demonstrates how to host a web application by configuring a client-server setup using Apache HTTP Server and NFS (Network File System) for shared content.

## 🔧 Tools & Technologies Used
- Apache HTTPD Server
- NFS (Network File System)
- Linux (Ubuntu, RedHat)

## 🖼️ Architecture
## ⚙️ Setup Steps

### 1. On NFS Server:
- Install NFS: `sudo apt install nfs-utils libnfsidmap`
- Enable service: `sudo systemctl enable rpcbind nfs-server`
- Start service: `sudo systemctl start rpcbind nfs-server rpc-statd nfs-idmapd`
- Create directory for NFS and give permissions : `chmod -R 777 /var/www/lady`
- Configure export directory: `/etc/exports`
- Allow client IP in `/etc/exports`

### 2. On Client:
- Install NFS client: `sudo apt install libnfs-utils rpcbind nfs-common`
- Mount NFS directory: `sudo mount <server-ip>:/shared /var/www/html`

### 3. Configure Apache:
- Set DocumentRoot to NFS mount
- Enable site and restart Apache

