# Install-firewalld
# Step 1 – Install Firewalld on Ubuntu 22.04|20.04|18.04
```bash
sudo apt update
sudo apt install firewalld

sudo systemctl enable firewalld
sudo systemctl start firewalld
```
#### Confirm that the service is running:
```bash
$ sudo firewall-cmd --state
running
```
# Step 2: Using Firewalld on Ubuntu22.04|20.04|18.04
1. List all firewall rules configured
```bash
$ sudo firewall-cmd --list-all
```
2. Get a list of all services that can be enabled using a name
   ```bash
   $ sudo firewall-cmd --get-services
   ```
3. Enable http service
   ```bash
   sudo firewall-cmd --add-service=http --permanent
   ```
4.  Enable both http and https on a single line
   ```bash
   sudo firewall-cmd --permanent --add-service={http,https} --permanent
   ```
5. Enable TCP port 7070
```bash
sudo firewall-cmd --add-port=7070/tcp --permanent
```
6.  Enable UDP port 514
 ```bash
sudo firewall-cmd --add-port=514/udp --permanent
```
7. Create a new zone
   ```bash
    sudo firewall-cmd --new-zone=myzone --permanent
   ```
8. Allow access to a port from specific subnet/IP
   ```bash
      sudo firewall-cmd --permanent --add-rich-rule='rule family="ipv4" source address="103.191.50.14" accept' --permanent
   ```
9. List all rich rules
    ```bash
    sudo firewall-cmd --list-rich-rules
   ```
