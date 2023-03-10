
# docker-nifi
A simple setup for running NiFi using docker images.

# Prerequisites

Docker

# Docker image
```
git clone https://github.com/Chegashi/nifiKafkaLabs.git
```


# Useful Docker Aliases that Make Docker Less Complex
Stop one or more running containers
```
docker stop $(docker ps -aq)
```
Remove one or more services
```
docker rmi -f $(docker images -aq)
```
Remove one or more services
```
docker rmi -f $(docker images -aq)
```

# Set up
```
cd nifiKafkaLabs/v2
```

```
docker-compose up
```

```
docker ps
```


```
docker exec -it nifi /bin/sh
```
inside nifi container
```
cat /opt/nifi/nifi-current/logs/nifi-app.log | grep "Generated"
```
exmple  <br><br>
Generated Username \[02573c37-202c-4f86-a019-42bc68d25e54] <br>
Generated Password \[/UchCB0XxaCkuV6BxYS73dS3Y/mfbUH8]
<br>
<br>
[**Visit the nifi website.**](https://localhost:8443/nifi)
<br>
<br>



we’ll create a Kafka topic by running the following command.

```
docker-compose exec kafka kafka-topics --create --topic test --partitions 1 --replication-factor 1 --if-not-exists --bootstrap-server localhost:9092
```

Verify it worked correctly.
```
docker-compose exec kafka kafka-topics --list --bootstrap-server localhost:9092

docker-compose exec kafka kafka-topics --describe --bootstrap-server localhost:9092  
```

```
docker cp Offres_emploi.csv nifi:/tmp/Offres_emploi.csv
```

```
docker exec -it kafka kafka-console-consumer --bootstrap-server localhost:9092 --topic test --from-beginning
docker exec -it kafka kafka-console-producer --broker-list localhost:9092 --topic test
docker exec -i kafka kafka-console-producer --broker-list localhost:9092 --topic test < Offres_emploi.csv 
```