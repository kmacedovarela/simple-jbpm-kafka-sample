Simple jBPM Kafka Integration Sample
=======================

## Pre Reqs

- Project tested with jBPM 7.44 / Available on RHPAM 7.9+
- Project tested on JDK 11

## Set up your environment:

1. To start the kafka environment, let's clone this repo:

`$ git clone https://github.com/hguerrero/amq-examples.git `

2. Enter the folder

`cd amq-examples/strimzi-all-in-one/`

3. Start Kafka

`docker-compose up`

4. In another tab, create the Kafka topic:

`docker-compose exec kafka bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic jbpm-task-events`



## Inside jBPM / RHPAM

1. Install the Kafka WIH in BC (Settings > Custom Tasks > KafkaPublishMessages)
2. Clone this project into business central
3. Deploy this project
4. Start a process instance



## Tracking the kafka topic

You can use kafkacat to track the topic. 

`$ kafkacat -b 127.0.0.1:9092 -t jbpm-task-events`

Example outputs when the messages are received

````
% Reached end of topic jbpm-task-events [0] at offset 0
Karina event for APAC
% Reached end of topic jbpm-task-events [0] at offset 1
````





