# kafka-python

# installation and running steps for Kafka Python on Windows:

1. Install Python: If you don't have Python installed on your system, go to the Python official website (https://www.python.org/downloads/windows/) and download and install the latest version of Python.

2. Install Kafka: Download the latest version of Kafka from the official website (https://kafka.apache.org/downloads) and extract it to a location on your computer.

3. Install the Kafka Python library: Open a command prompt or terminal and run the following command to install the Kafka Python library:

```
pip install kafka-python
```

4. Start Zookeeper and Kafka server: Open a new command prompt or terminal and navigate to the Kafka directory that you extracted earlier. Then, run the following commands to start Zookeeper and Kafka server:

```
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
```

```
.\bin\windows\kafka-server-start.bat .\config\server.properties
```

5. Create a Kafka topic: Open another command prompt or terminal and navigate to the Kafka directory. Then, run the following command to create a topic:

```
.\bin\windows\kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
```

6. Produce messages: In the same command prompt or terminal, run the following command to start producing messages to the test topic:

```
.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic test
```

7. Consume messages: Open a new command prompt or terminal and navigate to the Kafka directory. Then, run the following command to start consuming messages from the test topic:

```
.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic test --from-beginning
```

8. Write Kafka Python code: Open a code editor and write Python code to produce or consume messages from the Kafka topic. Here's an example code snippet to produce messages:

```
from kafka import KafkaProducer

producer = KafkaProducer(bootstrap_servers=['localhost:9092'])
producer.send('test', b'Hello, World!')
producer.flush()
```

And here's an example code snippet to consume messages:

```
from kafka import KafkaConsumer

consumer = KafkaConsumer('test', bootstrap_servers=['localhost:9092'])
for message in consumer:
    print(message)
``` 

That's it! You should now be able to install and run Kafka Python on Windows.
