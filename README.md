
# docker-kafka-nifi
A very simple setup for running a kafka cluster using docker images. It requires a zookeeper cluster and I have provided the same in another repo.

# The Need
There are lots of kafka docker images that help you to run a standalone version (with an inbuilt zookeeper or not) on a single node. These images help you to have a single node of kafka and doesn't provide you with high availability. This particular repo helps you in achieving a cluster (high availability) using simple scripts and docker.

# Prerequisites

Docker

# Docker image
```
git clone Chegashi/nifiKafkaLabs
```

# Setting up a kafka cluster
```
cd nifiKafkaLabs
docker-compose up
docker ps
open "https://localhost:8443/nifi"
docker exec -it nifikafkasmm_kafka_1 /bin/sh
cat /opt/nifi/nifi-current/logs/nifi-app.log | grep "Generated"
docker exec nifikafkasmm_kafka_1 kafka-topics --bootstrap-server nifikafkasmm_kafka_1:9092 --create --topic quickstart
```


