# Apache Ranger Docker POC (Proof of Concept)
- Apache Ranger Docker Cluster for POC with Hadoop Environment(HDFS, Hive, Presto)

# How to start
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



_____________________________
if you move into the ‘datanode’ container and try to access the HDFS through a non-owner user(hive), you are blocked.

# in your terminal
```
docker exec -it datanode bash# in the 'datanode' container as root user
useradd hive
su hive# in the 'datanode' container as hive user
/opt/hadoop-3.2.1/bin/hdfs dfs -ls /user/hive
ls: Permission denied: user=hive, access=EXECUTE, inode="/user/hive"
```