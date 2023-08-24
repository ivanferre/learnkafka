# Learn Kafka

## Sources

- Youtube Playlist by Confluent: [Apache Kafka Tutorials | Kafka 101](https://youtu.be/j4bqyAMMb7o?si=q3fkq1f65gJSKO99)

- Link from Sean: <https://developer.confuluent.io/courses/apache-kafka/events/>

- Links from Confluent Site:
  - Apache Kafka® Quick Start: <https://developer.confluent.io/quickstart/kafka-on-confluent-cloud/>

- [Learn Apache Kafka® & Flink®](https://developer.confluent.io/courses/)

- <https://www.tutorialspoint.com/apache_kafka/index.htm>

- <https://kafka.apache.org/intro>

## Kafka Events

Event = Something that has happened.
Event = Notification + State.

## Cloud Kafka

See config directory.

## Consumers Hand-On

```bash
    virtualenv env
    source env/bin/activate
    pip install confluent-kafka
    confluent kafka cluster describe
    # note the host and port from endpoint

    confluent api-key create --resource <ID>

    confluent api-key use <api-key> --resource

    # create config.ini
    [default]
    bootstrap-servers=<host:port> # taken from endpoint
    security.protocol=SASL_SSL
    security.mechanisms=PLAIN
    sasl.username=<api key>
    sasl.password=<api secret>

    [consumer]
    group.id=python.blablabla
    auto.offset.reset=earliest # to start reading from the beginning of the topic if no commited offsets exist.
```

## Questions

1. Consumers read from Partitions or from Topics?
2. Consumers and Producers work with Streams or with Topics?
