# Kafka-Integrated Microservices

This repository contains a set of microservices integrated with Kafka for message communication.

## Installation Steps

### 1. Java Installation
Install Java 8 or later. You can download Java from [Oracle's website](https://www.oracle.com/java/technologies/javase/javase8-archive-downloads.html).

### 2. Kafka Installation
Install Kafka by downloading it from [Kafka's official website](https://kafka.apache.org/downloads).

#### 2a. Starting Zookeeper
Start Zookeeper using the following command:
```bash
bin/zookeeper-server-start.sh config/zookeeper.properties
```

#### 2b. Starting Kafka
Start Kafka using the following command:
```bash
bin/kafka-server-start.sh config/server.properties
```

Reference: [Kafka Quickstart Guide](https://kafka.apache.org/quickstart)

## Project Setup

### 3. Clone and Open Project
Clone the project and open the `kafka-microservices` folder in IntelliJ IDEA.

### 4. Configuration
Define consumer and producer properties in `kafka-microservices/src/main/resources/application.properties`.

### 5. Kafka Topic Setup
Create a topic inside Kafka Server by configuring `KafkaTopicConfig.java` in `kafka-microservices/src/main/java/kafkamicroservices/config/`.

### 6. Producer Service
Implement the Producer Service in `KafkaProducer.java` located at `kafka-microservices/src/main/java/kafkamicroservices/kafka/`.

### 7. REST Controller
Create a REST Controller in `MessageController.java` at `kafka-microservices/src/main/java/kafkamicroservices/controller/`.

### 8. Publishing a Message
Publish a message through a REST call using:
```
http://localhost:8080/api/v1.0/kafka/publish?message=This is a sample Kafka microservices integration!
```
Expected browser output: "Message sent to the topic"

### 9. Reading Messages Locally
Read messages locally using the command:
```bash
bin/kafka-console-consumer.sh --topic sample --from-beginning --bootstrap-server localhost:9092
```
Expected local output: "This is a sample Kafka microservices integration!"

### 10. Reading Messages Using Consumer
Check `KafkaConsumer.java` in `kafka-microservices/src/main/java/kafkamicroservices/kafka/` for reading messages in Spring.
