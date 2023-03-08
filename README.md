
# docker-nifi
A simple setup for running NiFi using docker images.

# Prerequisites

Docker

# Docker image
```
git clone Chegashi/nifiKafkaLabs
```

# Set up
```
cd nifiKafkaLabs
docker-compose up
docker ps
open "https://localhost:8443/nifi"
docker exec -it nifikafkasmm_kafka_1 /bin/sh
cat /opt/nifi/nifi-current/logs/nifi-app.log | grep "Generated"
docker exec nifikafkasmm_kafka_1 kafka-topics --bootstrap-server nifikafkasmm_kafka_1:9092 --create --topic quickstart
```


