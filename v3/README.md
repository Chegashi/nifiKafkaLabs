# Apache Ranger Docker POC (Proof of Concept)
- Apache Ranger Docker Cluster for POC with Hadoop Environment(HDFS, Hive, Presto)

# How to start

```
git clone https://github.com/Chegashi/nifiKafkaLabs.git
cd nifiKafkaLabs/v3
```

```
docker network create ranger-env
```

```
cd docker-composes/ranger
```

```
docker-compose up -d --build
```

```
cd ../hadoop
```

```
docker-compose up -d --build
```

After you wait for 30 ~ 60 seconds, you can check http://localhost:6080 with the default username/password (admin/rangeradmin1):
