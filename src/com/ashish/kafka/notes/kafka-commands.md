===============
kafka commands:
===============
bin/kafka-console-consumer.sh --zookeeper localhost:2181 —topic Hello-Kafka --from-beginning

brokers started:
----------------
bin/kafka-server-start.sh config/server.properties

Single Node Single Broker Cluster:
----------------------------------
bin/kafka-console-producer.sh --broker-list localhost:9092 --topic Hello-Kafka
bin/kafka-console-consumer.sh --zookeeper localhost:2181 —-topic Hello-Kafka --from-beginning --whitelist Hello-Kafka

Single Node Multiple Broker Cluster:
------------------------------------
Started 2 brokers and 1 started earlier:
bin/kafka-server-start.sh config/server-one.properties
bin/kafka-server-start.sh config/server-two.properties

producer:
bin/kafka-console-producer.sh --broker-list localhost:9092  --topic Multibrokerapplication

consumer:
bin/kafka-console-consumer.sh --zookeeper localhost:2181 --topic Multibrokerapplication --from-beginning

list all the topics:
--------------------
bin/kafka-topics.sh --list --zookeeper localhost:2181

modify and delete a topic:
--------------------------
bin/kafka-topics.sh --zookeeper localhost:2181 --alter --topic Hello-kafka --parti-tions 2
bin/kafka-topics.sh --zookeeper localhost:2181 --delete --topic Hello-kafka

check the daemons process running:
----------------------------------
$ jps
821 QuorumPeerMain  = ZooKeeper daemon
928 Kafka           = kafka daemon
931 Jps
