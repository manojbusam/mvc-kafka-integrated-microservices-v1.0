# mvc-kafka-integrated-microservices-v1.0
Microservice managing Producer and Consumer Near Real Time(NRT) data/ messages from Kafka Server 


![Screenshot 2023-02-04 at 12 22 54 AM](https://user-images.githubusercontent.com/44409170/216750330-d4ca5d7b-f0fe-43ac-80aa-bf0c9efcb775.png)


Step-by-step:

1. Install Java 8+

https://www.oracle.com/java/technologies/javase/javase8-archive-downloads.html

2. Install kafka

https://kafka.apache.org/downloads

2a. Reference: 

https://kafka.apache.org/quickstart

2b. starting zookeeper:

bin/zookeeper-server-start.sh config/zookeeper.properties

2c. starting kafka:

bin/kafka-server-start.sh config/server.properties

3. Clone the project and open the following folder in IntelliJ

https://github.com/manojbusam/mvc-kafka-integrated-microservices-v1.0/tree/main/kafka-microservices

4. Define the consumer and producer properties at:

https://github.com/manojbusam/mvc-kafka-integrated-microservices-v1.0/blob/main/kafka-microservices/src/main/resources/application.properties

5. Creating a topic inside Kafka Server:

https://github.com/manojbusam/mvc-kafka-integrated-microservices-v1.0/blob/main/kafka-microservices/src/main/java/kafkamicroservices/config/KafkaTopicConfig.java


6. Creating a Producer Service:

https://github.com/manojbusam/mvc-kafka-integrated-microservices-v1.0/blob/main/kafka-microservices/src/main/java/kafkamicroservices/kafka/KafkaProducer.java

7. Creating a REST Controller:
https://github.com/manojbusam/mvc-kafka-integrated-microservices-v1.0/blob/main/kafka-microservices/src/main/java/kafkamicroservices/controller/MessageController.java

8. Publishing a message through REST call on browser:
http:localhost:8080/api/v1.0/kafka/publish?message=This is a sample kafka microservices integartion!

Expected output in browser:   
Message sent to the topic

9. Reading the messages in local:

bin/kafka-console-consumer.sh --topic sample --from-beginning --bootstrap-server localhost:9092

Expected output in local: 
"This is a sample kafka microservices integartion!"

10. Reading the messages using consumer:


Expected output in Spring:
Message received -> This is a sample kafka microservices integartion!