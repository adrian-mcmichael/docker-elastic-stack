# docker-elastic-stack

## Requirements

Install the Docker toolbox at at least version 1.11.0

## Description

The following components are created when this docker file is created:

* Spins up a two node Elasticsearch cluster (available on ports 9200 and 8200 respectively)
* Installs Marvel plugin on the cluster.
* Spins up Kopf as a standalone server on port 8080.
* Mounts Elasticsearch data containers.
* Spins up Kibana with Sense, Timelion and Marvel.

Enhancements to come:

* Add the logstash component

## Running

```bash
docker-compose up
```
