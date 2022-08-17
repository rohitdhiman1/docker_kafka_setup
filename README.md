# docker_kafka_setup

Repo to kickstart kafka on docker

Prerequisites 
1. Docker desktop installed on the machine 
2. Docker compose (comes bundled with docker desktop for mac)

Tested with Docker version 20.10.17, build 100c701 and docker-compose version 1.29.2, build 5becea4c

`docker compose -f docker-compose.yaml up -d`

execute an interactive bash shell on the container

`docker exec -it kafka bash`

Once you're inside the shell of the container, invoke producer, consumer and check topics 

Navigate to the bin directory of kafka (make sure you're in kafka container, not in zookeeper)

`cd /opt/kafka/bin`

Producer
`kafka-console-producer.sh --bootstrap-server localhost:9092 --topic topic1`

Consumer 
`kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic topic1 --from-beginning`

Topics 
List Topics 
`kafka-topics.sh --bootstrap-server localhost:9092 --list`
Describe a topic 
`kafka-topics.sh --bootstrap-server localhost:9092 --topic topic1 --describe`
Create a topic 
`kafka-topics.sh --bootstrap-server localhost:9092 --create --topic topic2`



