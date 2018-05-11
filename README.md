# About this repository

This repository contains an example of how to configure a remote chunking job
in Spring Batch. The master step reads numbers from 1 to 6 and sends two chunks
{1, 2, 3} and {4, 5, 6} to workers for processing and writing.

The master and worker configurations are defined in `MasterConfiguration` and
`WorkerConfiguration` classes respectively.

The sample uses an embedded ActiveMQ JMS broker (for simplicity) but 
communication between the master and workers is still done through JMS queues
and Spring Integration channels over the wire through a TCP port 
(default port `61616` of ActiveMQ which can be configured in `application.properties`).

# Running the sample

### From the IDE

Run the JUnit test `io.github.benas.RemoteChunkingJobTest.testRemoteChunkingJob`

### From the CLI

`$>mvn test`
