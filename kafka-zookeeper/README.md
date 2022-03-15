# Single Node Setup
A single node Kafka broker setup would meet most of the local development needs, so let's start by learning this simple setup.
# Change docker-compose.yml meet system specification
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
# Check the verbose logs while the containers are starting up and verify that the Kafka server is up
```bash
docker-compose logs kafka | grep -i started
kafka        | [2022-03-15 05:39:07,431] INFO [SocketServer listenerType=ZK_BROKER, nodeId=1] Started data-plane acceptor and processor(s) for endpoint : ListenerName(LISTENER_DOCKER_INTERNAL) (kafka.network.SocketServer)
kafka        | [2022-03-15 05:39:07,439] INFO [SocketServer listenerType=ZK_BROKER, nodeId=1] Started data-plane acceptor and processor(s) for endpoint : ListenerName(LISTENER_DOCKER_EXTERNAL) (kafka.network.SocketServer)
kafka        | [2022-03-15 05:39:07,440] INFO [SocketServer listenerType=ZK_BROKER, nodeId=1] Started socket server acceptors and processors (kafka.network.SocketServer)
kafka        | [2022-03-15 05:39:07,463] INFO [KafkaServer id=1] started (kafka.server.KafkaServer)
```
# Connection Using Kafka Tool
[Download  Offset Explorer (formerly Kafka Tool)](https://kafkatool.com/download.html)
