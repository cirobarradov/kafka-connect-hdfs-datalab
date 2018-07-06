# Kafka Connect Suite of Cloud Storage Connectors

*kafka-connect-storage-cloud* is a suite of [Kafka Connectors](http://kafka.apache.org/documentation.html#connect)
designed to be used to copy data between Kafka and public cloud stores, such as Amazon S3. The currently available connectors are listed below:

## Kafka Connect Sink Connector for Azure Blob Storage

Configuration parameters:

*azblob.storageaccount.connectionstring=<connection string>
*azblob.containername=<container name>

name=azblob-sink
connector.class=io.confluent.connect.azblob.AzBlobSinkConnector
tasks.max=1
topics=<topic_name>

flush.size=3

storage.class=io.confluent.connect.azblob.storage.AzBlobStorage
#format.class=io.confluent.connect.azblob.format.avro.AvroFormat
format.class=io.confluent.connect.azblob.format.json.JsonFormat
schema.generator.class=io.confluent.connect.storage.hive.schema.DefaultSchemaGenerator
partitioner.class=io.confluent.connect.storage.partitioner.DefaultPartitioner

schema.compatibility=NONE
#partition.field.name=
#partition.duration.ms=
#path.format=
#locale=
#timezone=


# Development

To build a development version you'll need a recent version of Kafka. You can build
*kafka-connect-storage-cloud* with Maven using the standard lifecycle phases.


# Contribute

- Source Code: https://github.com/confluentinc/kafka-connect-storage-cloud
- Issue Tracker: https://github.com/confluentinc/kafka-connect-storage-cloud/issues


# License

The project is licensed under the Apache 2 license.
