---
---

# System State

State, or data, is the heaviest piece of your architecture. Data has mass. It's difficult to move, and it can cause damage in large quantities or high velocities. Stand clear of data in motion, and mind the structural integrity of the systems that hold data at rest.

There are a variety of ways to store state intentionally, and even more ways to store it unintentionally.

# Data At Rest

Also see [Encryption At Rest](/security/encryption/at-rest.html).

## [Relational Databases](relational-db/)

Relational databases are useful for storing data that relate to each other. This kind of data is easy to describe with tools like block diagrams and UML. If your data can be described as "having" other data, or being "owned" by other data, then consider relational databases.

## [Key-Value Stores](key-value-store/)

If you _really_ need arbitrary blobs of unstructured data, a key/value store might be for you. You should plan to treat these values as opaque blobs, to be retireved by the key.

## [Document Stores](document-db/)

A document store is conceptually similar to a Key/Value store, but the values are transparent to the database. You may be able to query into the documents themselves. Be wary of trying to store relational data in a document store, you will regret it eventually.

## [File Store](file-store/)

A file store, or object store, or whatever you want to call it, is conceptually similar to a Key-Value store, except the values can be very large. It's worth considering this as a separate class of state storage, because some of the assumptions about throughput and consistency can be different when dealing with "heavy" payloads.

# Data In Motion

Also see [Encryption In Transit](/security/encryption/in-transit.html).

## [Queues](queues/)

* SQS
* RabbitMQ

## [Streams](streams/)

It seems like there should be a whole category of tools like this, but [Kafka](streams/kafka) is the only one I'm aware of.

## [Messaging](messaging/)

* SNS
* ZeroMQ
* ActiveMQ
