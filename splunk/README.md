# Docker-Compose Splunk
Docker-compose file for splunk server.

## Deployment:
````
git clone https://github.com/sonnyyu/log-file-analysis/
cd log-file-analysis/splunk
nano  docker-compose.yml 
````
NOTE: change password before turning up container.
## Start splunk
```bash
docker-compose up -d 
```
## Usage:
- Use Docker host IP address via http://[host IP]:8000
- 
- Login via credentials user: admin, password with one you put on the docker-compose yml.




