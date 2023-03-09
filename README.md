
# docker-nifi
A simple setup for running NiFi using docker images.

# Prerequisites

Docker

# Docker image
```
git clone https://github.com/Chegashi/nifiKafkaLabs.git
```

# Set up
```
cd nifiKafkaLabs
```

```
docker-compose up
```

```
docker-compose ps
```
get the name of nifi container in my case the name is :  ***nifikafkalabs_nifi_1***
line 2 column 1
![alt text](./image.png)

```
docker exec -it [nifi_container_name] /bin/sh
```

```
cat /opt/nifi/nifi-current/logs/nifi-app.log | grep "Generated"
```

get :
Generated Username [******************************]
Generated Password [******************************]

```
open "https://localhost:8443/nifi"
```

```
docker exec nifikafkasmm_kafka_1 kafka-topics --bootstrap-server nifikafkasmm_kafka_1:9092 --create --topic quickstart
```


