
```shell script
# Mac
brew install kafka
(OR)
# Download kafka tar, untar it and set the path
https://kafka.apache.org/downloads
```

Validate
```shell script
kafka-topics.sh
# check if the above command runs. 
```

## Start the server
```shell script
cd ~/SOFTWARES/kafka_2.13-2.8.0
# update zookeeper data director 
vim config/zookeeper.properties
#/Users/m_116394/SOFTWARES/kafka_2.13-2.8.0/data/zookeeper
#Start zookeeper server
zookeeper-server-start.sh config/zookeeper.properties


# Update kafka server properties. 
vim config/server.properties
#/Users/m_116394/SOFTWARES/kafka_2.13-2.8.0/data/kafka
#Start kafka server
bin/kafka-server-start.sh config/server.properties
```
