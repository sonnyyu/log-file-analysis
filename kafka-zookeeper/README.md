# Single Node Setup
A single node Kafka broker setup would meet most of the local development needs, so let's start by learning this simple setup.
# Docker-compose.yml Configuration
```bash
environment:
      KAFKA_ADVERTISED_LISTENERS: LISTENER_DOCKER_INTERNAL://kafka:19092,LISTENER_DOCKER_EXTERNAL://192.168.1.204:9092
...

```
