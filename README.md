# mvc-kafka-integrated-microservices-v1.0
Microservice that produces and subscribes near real time data/ messages from Kafka Server 


![Screenshot 2023-02-04 at 12 22 54 AM](https://user-images.githubusercontent.com/44409170/216750330-d4ca5d7b-f0fe-43ac-80aa-bf0c9efcb775.png)


Step-by-step:

1. Install Java 8+
https://www.oracle.com/java/technologies/javase/javase8-archive-downloads.html

2. Install kafka
https://kafka.apache.org/downloads

2a. Reference: https://kafka.apache.org/quickstart

2b. starting zookeeper
bin/zookeeper-server-start.sh config/zookeeper.properties

2c. starting kafka
bin/kafka-server-start.sh config/server.properties
