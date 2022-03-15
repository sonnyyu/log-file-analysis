# Single Node Setup
A single node Kafka broker setup would meet most of the local development needs, so let's start by learning this simple setup.
# Docker-compose.yml Configuration
```bash
# 192.168.1.204 is Docker host ip address
environment:
      KAFKA_ADVERTISED_LISTENERS: LISTENER_DOCKER_INTERNAL://kafka:19092,LISTENER_DOCKER_EXTERNAL://192.168.1.204:9092
...
      KAFKA_JMX_HOSTNAME: 192.168.1.204
```
# Start Kafka Server
```bash
docker-compose up -d
```
# Test servers are listening on the respective ports
```bash
nc -z localhost 2181 -v
Connection to localhost port 2181 [tcp/*] succeeded!
nc -z localhost 9092 -v
Connection to localhost port 2181 [tcp/*] succeeded!
```
