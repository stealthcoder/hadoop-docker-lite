# Kafka docker image
This is a kafka docker image

##Version
0.8.2.1

##Building the image
```./build.sh```

##Usage
Start a cluster with zookeeper and kafka:

- ```docker-compose up -d ```

Add more brokers:

- ```docker-compose scale kafka=3```

Destroy a cluster:

- ```docker-compose stop```


##Notes
The default ```docker-compose.yml``` should be seen as a starting point. By default each broker will get a new port number and broker id on restart. Depending on your use case this might not be desirable. If you need to use specific ports and broker ids, modify the docker-compose configuration accordingly


##Automatically create topics

If you want to have kafka-docker automatically create topics in Kafka during creation, a ```KAFKA_CREATE_TOPICS``` environment variable can be
added in ```docker-compose.yml```.

Here is an example snippet from ```docker-compose.yml```:

        environment:
          KAFKA_CREATE_TOPICS: "INBOUND:1:2,OUTBOUND:1:1"

```INBOUND``` topic will have 1 partition and 2 replicas, ```OUTBOUND``` topic will have 1 partition and 1 replica.

##Custom environments variables
- Advertised hostname: ```KAFKA_ADVERTISED_HOST_NAME``` 
- Advertised port: ```KAFKA_ADVERTISED_PORT``` 
