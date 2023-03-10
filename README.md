# mvc-kafka-integrated-microservices-v1.0
Microservice managing Producer and Consumer Near Real Time(NRT) data/ messages from Kafka Server 


![Screenshot 2023-02-04 at 3 42 51 PM](https://user-images.githubusercontent.com/44409170/216788883-bbc6cf6e-35d9-47df-9e9d-67ff17c7c9fb.png)


## Step-by-step:


# 1. Install Java 8+

https://www.oracle.com/java/technologies/javase/javase8-archive-downloads.html

# 2. Install kafka

https://kafka.apache.org/downloads

# 2a. starting zookeeper:

bin/zookeeper-server-start.sh config/zookeeper.properties

# 2b. starting kafka:

bin/kafka-server-start.sh config/server.properties

# 2c. Reference: 

https://kafka.apache.org/quickstart

# 3. Clone the project and open the following folder in IntelliJ

https://github.com/manojbusam/mvc-kafka-integrated-microservices-v1.0/tree/main/kafka-microservices

# 4. Define the consumer and producer properties at:

kafka-microservices/src/main/resources/application.properties

# 5. Creating a topic inside Kafka Server:

kafka-microservices/src/main/java/kafkamicroservices/config/KafkaTopicConfig.java


# 6. Creating a Producer Service:

kafka-microservices/src/main/java/kafkamicroservices/kafka/KafkaProducer.java

# 7. Creating a REST Controller:
kafka-microservices/src/main/java/kafkamicroservices/controller/MessageController.java

# 8. Publishing a message through REST call on browser:
http:localhost:8080/api/v1.0/kafka/publish?message=This is a sample kafka microservices integartion!

Expected output in browser:   
Message sent to the topic

# 9. Reading the messages in local:

bin/kafka-console-consumer.sh --topic sample --from-beginning --bootstrap-server localhost:9092

Expected output in local: 
"This is a sample kafka microservices integartion!"

# 10. Reading the messages using consumer:

kafka-microservices/src/main/java/kafkamicroservices/kafka/KafkaConsumer.java

Expected output in Spring:
Message received -> This is a sample kafka microservices integartion!
