# BASIC CLI COMMAND

## <span style ="color:#87CFEB">DOCKER COMMAND</span>
### Login to The Container
```
docker exec -it <container_name> bash
```
it - interactive tty where -i keep it interactive and -t Open a terminal

## <span style ="color:#87CFEB">TOPICS</span>
### CREATE TOPICS
```
kafka-topics --create --topic test-topic --replication-factor 1 --partitions 4 --bootstrap-server kafka1:19092
```
### DELETE TOPICS
```
kafka-topics --delete --topic test-topic --bootstrap-server kafka1:19092
```
### LIST TOPICS
```
kafka-topics --bootstrap-server kafka1:19092 --list
```
### ALTER TOPICS
```
kafka-topics --bootstrap-server kafka1:19092 \
--alter --topic test-topic --partitions 40
```

## <span style ="color:#87CFEB">PRODUCERS</span>
### Without Key
```
kafka-console-producer --bootstrap-server kafka1:19092 \
--topic test-topic
```
### With Key
```
kafka-console-producer --bootstrap-server kafka1:19092 \
--topic test-topic \
--property "key.separator=-" --property "parse.key=true"
```

## <span style ="color:#87CFEB">CONSUMERS</span>
### Without Key
```
kafka-console-consumer --bootstrap-server kafka1:19092 \
                       --topic test-topic \
                       --from-beginning
```
### With Key
```
kafka-console-consumer --bootstrap-server kafka1:19092 \
                       --topic test-topic \
                       --from-beginning \
                       --property "key.separator= - " --property "print.key=true"
```


