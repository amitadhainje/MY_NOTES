# Apache Kafka

---

- Learning Links - https://www.youtube.com/watch?v=QkdkLdMBuL0&t=918s
- https://www.youtube.com/watch?v=B7CwU_tNYIE&t=1764s

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

## Kafka Stream APIs

- The Kafka Streams API in Apache Kafka is a client library used to process and transform data streams in real time. It allows you to read data from Kafka topics, apply operations like filtering, grouping, and aggregations, and write the results back to new topics. It runs inside your application (no separate cluster needed), is scalable, and handles fault tolerance automatically. It is commonly used for real-time analytics, data transformations, and building streaming pipelines.

## Paritions 

- In Apache Kafka, a **partition** is a division of a topic that allows data to be split and stored across multiple servers. This helps Kafka handle large volumes of data efficiently. Each partition stores messages in order and assigns them a unique offset. Partitions enable parallel processing, so multiple consumers can read data at the same time, improving performance and scalability.

## Consumer Groups in Kafka

- In Apache Kafka, a **consumer group** is a set of consumers that work together to read data from a topic. Instead of each consumer reading all the data, the partitions of a topic are divided among the consumers in the group. Each partition is read by only one consumer within the group at a time, which avoids duplication and enables parallel processing. This makes consumer groups important for scaling data consumption and handling large data streams efficiently.

## Kafka Brokers

- In Apache Kafka, a **broker** is a server that stores data and handles requests from producers and consumers. When a producer sends data, it goes to a broker, and when a consumer reads data, it fetches it from a broker. Each broker manages one or more topic partitions and is responsible for storing them on disk. Multiple brokers work together to form a Kafka cluster, which helps in distributing data, improving scalability, and ensuring fault tolerance. Stores messages on a disk for a configurable retention policy. Hence, Consumers can read the event multiple times and whenever they want. Replay of messages helps in historical data analysis.

## ZooKeeper in Kafka

Apache ZooKeeper is a distributed coordination service that was traditionally used by Apache Kafka to manage and coordinate the Kafka cluster. It helps Kafka by keeping track of important metadata such as which brokers are active, which broker is the leader for each partition, and cluster configuration details. ZooKeeper also helps in leader election, ensuring that if one broker fails, another broker automatically takes over as the leader. Additionally, it maintains synchronization between different brokers and keeps the system consistent. However, in newer versions of Kafka, ZooKeeper is being replaced by an internal mechanism called KRaft, which removes the dependency on ZooKeeper and simplifies the architecture.


## Kafka Raft (KRaft)

In Apache Kafka, **Kafka Raft (KRaft)** is a built-in consensus mechanism that replaces the need for Apache ZooKeeper. KRaft uses the Raft protocol to manage cluster metadata, leader election, and coordination between brokers. Instead of relying on an external system like ZooKeeper, Kafka now handles everything internally, making the architecture simpler and easier to manage. With KRaft, a set of Kafka nodes act as controllers that maintain metadata in a fault-tolerant way, ensuring consistency even if some nodes fail. This improves scalability, reduces operational complexity, and is the default approach in newer Kafka versions. 





