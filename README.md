# docker-elastic-stack

Provides an elasticsearch environment for testing logstash configurations
against sample logs.

## Requirements

Install the Docker toolbox at at least version 1.11.0

## Description

The following components are created when this docker file is created:

* Spins up a two node Elasticsearch cluster (available on ports 9200 and 8200 respectively)
* Installs Marvel plugin on the cluster.
* Spins up Kopf as a standalone server on port 8080.
* Mounts Elasticsearch data containers.
* Spins up Kibana with Sense, Timelion and Marvel.
* Spins up logstash (use initialise.sh script to create the directories local used to copy logstash logs and config from)

## Running

To initialise the folders that logstash will use to copy over its configuration
with any test logs.

```bash
./initialise.sh
```

Then put any test logstash configuration in the /logstash/config folder, logs
to ingest in the /logstash/logs folder and optionally logstash patterns in the
patterns folder and elasticsearch mapping templates in templates.

Then spin up the stack.

```bash
docker-compose up
```
