# Docker-Compose Splunk
Docker-compose file for splunk server.


## Deployment:
````
git clone https://github.com/rvincemt/docker-splunk.git
cd ./docker-splunk
vi docker-compose.yml 
````
### NOTE: change password before turning up container.
### Once done with changing the password, build and deploy docker container:

````
docker-compose up -d 
````

## Usage:
1. Go to server's IP address (or localhost if you're hosting it on the same PC) via http://127.0.0.1:9999

2. Login via credentials user: admin, password with one you put on the docker-compose yml.

3. Point your devices' rsyslog.conf to the server's ip and port 1514 as your remote syslog server.

* On Linux, this can be done via:
````
sudo echo "*. *     @@<server IP>:1514" >> /etc/rsyslog.conf
sudo systemctl restart rsyslog
````


* On Cisco devices, point log server to <server ip> port 1514.
  
* On PFSense/Opnsense, go to System>Settings>Logging Targets and add to logserver. 
  
  
4. 



