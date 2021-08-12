# Scenarios - Using Kafka CLI


## Start the server
```shell script
cd ~/SOFTWARES/kafka_2.13-2.8.0
zookeeper-server-start.sh config/zookeeper.properties
kafka-server-start.sh config/server.properties
```

## Create a topic with 3 partitions
```shell script
kafka-topics.sh --zookeeper 127.0.0.1:2181 --topic first_topic --create --partitions 3 --replication-factor 1
kafka-topics.sh --zookeeper 127.0.0.1:2181 --list
kafka-topics.sh --zookeeper 127.0.0.1:2181 --topic first_topic --describe

```

## Delete a topic
```shell script
kafka-topics.sh --zookeeper 127.0.0.1:2181 --topic second_topic --create --partitions 3 --replication-factor 1
kafka-topics.sh --zookeeper 127.0.0.1:2181 --topic second_topic --list
kafka-topics.sh --zookeeper 127.0.0.1:2181 --topic second_topic --delete
```

## Starting console producer
```shell script
kafka-console-producer.sh --topic first_topic --broker-list 127.0.0.1:9092
kafka-console-producer.sh --topic first_topic --broker-list 127.0.0.1:9092
 --producer-property acks=all


kafka-console-producer.sh --topic new_topic --broker-list 127.0.0.1:9092
kafka-topics.sh --zookeeper 127.0.0.1:2181 --list

```

## Changing default configuration
```shell script
vim config/server.properties
# Change some attributes - say default partition.
kafka-console-producer.sh --topic new_topic --broker-list 127.0.0.1:9092
kafka-topics.sh --zookeeper 127.0.0.1:2181 topic new_topic --describe
```

# Chat like
```shell script
# Producer window
kafka-console-producer.sh --topic first_topic --broker-list 127.0.0.1:9092

# Consumer window
kafka-console-consumer.sh --bootstrap-server 127.0.0.1:9092 --topic first_topic

# Read all messages from the beginning
kafka-console-consumer.sh --bootstrap-server 127.0.0.1:9092 --topic
 first_topic --from-beginning
```
