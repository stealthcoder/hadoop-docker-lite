# Hbase docker image
This is a hbase docker image

##Version
1.1.2

##Exposed ports
- HBase Master API port: 60000
- HBase Master Web UI: 60010
- Regionserver API port: 60020
- HBase Regionserver web UI: 60030

##Building the image       
```./build.sh```

##Usage
Start a cluster with zookeeper and hbase:

- ```docker-compose up -d ```

Destroy a cluster:

- ```docker-compose stop```


## Running hbase commands
- ```docker exec -it hbase bash```      
- ```hbase shell```
- Type the hbase commands

## Accessing Hbase UI
- (http://localhost:60010)