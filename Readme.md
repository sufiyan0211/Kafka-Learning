Kafka 
===


## Lesson 1:
1. Kafka Installation.
2. Zookeeper Installation.
3. Running single node Kafka cluster.
4. Running Single node Zookeeper cluster.


## Run Zookeeper Server foreground: 
`./zkServer.sh start-foreground`

## Run Zookeeper Server background: 
`./zkServer.sh start`

## Run Kafka Server foreground: 
`./kafka-server-start.sh ../config/server.properties`

## Run Kafka Server background: 
`./kafka-server-start.sh -daemon ../config/server.properties`

## Check Zookeeper status: 
`echo stat | nc localhost 2181`

## Check Kafka server status: 
`echo dump | nc localhost 2181 | grep brokers`

## Run Kafka Server foreground: 
`./kafka-server-start.sh ../config/server.properties`


## Lesson 2:
1. Create Topic from Command Line
2. Working with console Producer
3. Working with console Consumer
4. Commands to check <b>Topic Properties</b> and <b>Consumer Group Properties</b>.


## Create a Topic
`./kafka-topics.sh --bootstrap-server localhost:9092 --create --topic myTopic --partitions 1 --replication-factor 1`

## List all Topic
`./kafka-topics.sh --bootstra-server localhost:9092 --list`

## Describe a Topic
`./kafka-topics.sh --bootstrap-server localhost:9092 --describe --topic <NameOfTopic>`

## Produce messages in a Tpoic
`./kafka-console-producer.sh --bootstrap-server localhost:9092 --topic <NameOfTopic>`

## Consume messages from a Topic 
`./kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic <NameOfTopic>`

## Consume messages from a Topic all from beginning
`./kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic <NameOfTopic> --from-beginning`

## List Consumer Groups
As we started consuming messages thats why consumer group has been created</br>
`./kafka-consumer-groups.sh --bootstrap-server localhost:9092 --list`

## Describe a Consumer Group
`./kafka-consumer-groups.sh --bootstrap-server localhost:9092 --describe --group <NameOfConsumerGroup>`

## Lesson 3
1. Zookeeper cluster setup with 3 zookeeper nodes.


1. Try run odd number of zookeeper nodes because it is for zookeeper service to choose zookeeper leader
2. Create Multiple ZK 
3. Add zoo.cfg

    tickTime=2000
    initLimit=10
    syncLimit=5
    dataDir=/tmp/zookeeper-1
    clientPort=2181
    maxClientCnxns=60
    4lw.commands.whitelist=*
    server.1=localhost:2788:3788
    server.2=localhost:2888:3888
    server.3=localhost:2988:3988
