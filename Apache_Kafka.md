# Apache Kafka

---

## Why Apache Kafka

- Apache Kafka is used when we need to handle large amounts of data in real time in a reliable and scalable way. In modern systems, applications continuously generate data such as logs, transactions, user activity, and events. Kafka helps in collecting and processing this data as it is generated, instead of waiting for batch processing.
- One of the main reasons Kafka is popular is its ability to handle very high data volume with low delay. It can process millions of messages per second, making it suitable for real-time analytics, monitoring systems, and event-driven applications. It also helps in decoupling systems, meaning the application sending data (producer) and the application reading data (consumer) do not need to directly interact with each other. This makes the system more flexible and easier to scale.
- Kafka is also fault-tolerant because it replicates data across multiple servers, so even if one server fails, data is not lost. It is distributed by design, which means we can scale it easily by adding more servers. Because of these features, Kafka is widely used in big data ecosystems along with tools like Apache Spark and Hadoop.

## What is Apache Kafka

- Apache Kafka is a distributed event streaming platform that allows applications to send, store, and read streams of data in real time. It acts like a central system where data is continuously written by producers and read by consumers.
- In simple terms, Kafka works like a high-speed messaging system. One application sends data to Kafka, and other applications can read that data whenever they need it. Kafka stores the data for a certain period, so consumers can read it even later if required.
- For example, in a banking system, every transaction can be sent to Kafka. Then different systems such as fraud detection, analytics, and reporting can read the same data independently and in real time. This makes Kafka very useful in building scalable and real-time data pipelines.


## Important Kafka Terms

- In Kafka, a **producer** is an application that sends data to Kafka, while a consumer is an application that reads data from Kafka. Data in Kafka is organized into topics, which are like categories or streams of data, such as logs or transactions.
- Each topic is divided into partitions. **Partitions** allow Kafka to handle large data by distributing it across multiple servers and enabling parallel processing. Every message in a partition has a unique identifier called an offset, which helps track the order of messages and what has been consumed.
- Kafka runs on servers called **brokers**, and a group of brokers forms a Kafka cluster. To ensure reliability, Kafka replicates data across multiple brokers. In each partition, one broker acts as the leader (handling reads and writes), while others act as followers (replicating data).
- **Consumers** can be grouped into consumer groups. Each consumer in a group reads from different partitions, which allows data to be processed in parallel without duplication. Kafka stores data as an append-only log, meaning data is continuously added and not modified.
- Kafka also provides additional components like Kafka Streams for processing data in real time and Kafka Connect for integrating Kafka with external systems like databases and APIs. Earlier, Kafka used Apache ZooKeeper for managing the cluster, but newer versions use a built-in system called KRaft. Overall, Kafka can be thought of as a distributed system that combines messaging, storage, and real-time data processing in a single platform.

## Chain of Events in Apache Kafka

- In Apache Kafka, a **chain of events** simply means the flow of data as it moves step-by-step from one system to another. Kafka is built around events, where an event is just a piece of data (like a transaction, log, or user action).
- The chain of events starts when a **producer** creates an event and sends it to a Kafka topic. This event is then stored in Kafka inside a partition as part of an ordered log. Once the event is stored, one or more **consumers** can read that event from the topic. These consumers can then process the data and may even generate new events, which are again sent back to Kafka. This creates a continuous flow or chain.

- In simple terms, the chain looks like this:

**Producer → Kafka Topic → Consumer → Processing → (Optional: New Producer)**

For example, in a real-world scenario like an e-commerce system, when a user places an order, the order service sends an event to Kafka. This event is then consumed by multiple systems such as payment processing, inventory management, and notification services. Each of these systems can act on the event and may produce new events, continuing the chain. This chain of events allows systems to work independently while still staying connected through Kafka. It helps in building scalable, real-time, and event-driven architectures where data flows continuously between different components.

- Kafka Stream APIs: The Kafka Streams API in Apache Kafka is a client library used to process and transform data streams in real time. It allows you to read data from Kafka topics, apply operations like filtering, grouping, and aggregations, and write the results back to new topics. It runs inside your application (no separate cluster needed), is scalable, and handles fault tolerance automatically. It is commonly used for real-time analytics, data transformations, and building streaming pipelines.

- In Apache Kafka, a **partition** is a division of a topic that allows data to be split and stored across multiple servers. This helps Kafka handle large volumes of data efficiently. Each partition stores messages in order and assigns them a unique offset. Partitions enable parallel processing, so multiple consumers can read data at the same time, improving performance and scalability.

