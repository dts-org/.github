# Data Streaming Infrastructure 

This project demonstrates a real-time data streaming architecture built around Apache Kafka, connecting a web application and a transactional database (as producers) to analytics and storage systems (as consumers), using Kafka Connect connectors and a Schema Registry to manage data schemas.
The system covers two parallel data flows: 
- streaming user interactions from the web app into Cassandra (via Avro schemas),
- Change Data Capture (CDC) from the transactional database into a MinIO data lake (via Debezium).

The diagram below shows the overall data flow - from producers, through the Kafka cluster and connectors, to consumers:

<img width="1733" height="620" alt="data_streaming" src="https://github.com/user-attachments/assets/581c068d-2b72-4ba2-ad8c-7f1e95672ae9" />


# Respoitories

Each component lives in its own repository:

- [stationery-store](https://github.com/dts-org/stationery-store) — web app, Kafka producer
- [kafka-streaming-platform](https://github.com/dts-org/kafka-streaming-platform) — Kafka cluster & connector configs
- [cassandra-product-reviews](https://github.com/dts-org/cassandra-product-reviews) — Cassandra cluster, streaming consumer
- [minio-data-lake](https://github.com/dts-org/minio-data-lake) — MinIO data lake, CDC consumer
