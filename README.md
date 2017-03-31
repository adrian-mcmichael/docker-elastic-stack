# docker-elastic-stack

Provides an Elasticsearch environment for testing Logstash configurations
against sample logs.

## Requirements

Install the Docker toolbox at at least version 1.13.0

Make sure that you have given a reasonable amount of RAM and CPUs to your local Docker:
[https://docs.docker.com/docker-for-mac/#advanced]()

At least 4GB and 2 CPUs is recommended.

## Description

The following components are created when this docker file is created:

* Spins up a two node Elasticsearch cluster (available on ports 9200 and 8200 respectively)
* Installs the following plugins on the cluster:
   * Marvel
   * Watcher
   * License
* Spins up Kopf as a standalone server on port 8080.
* Mounts Elasticsearch data containers.
* Spins up Kibana with Sense, Timelion, Prelert Swimlane Visualisation and Marvel.
* Spins up logstash (use initialise.sh script to create the directories local used to copy logstash logs and config from)
* Spins up an instance of mailhog for testing sending emails through Watcher
   * [https://github.com/mailhog/MailHog]()

## Setup

Add an Elastic license.json file to the `license-call` directory next to the Dockerfile. This allows Watcher and Marvel to function without their trial period expiring. This license can be obtained
from your Elastic support portal account if you have a support contract.

If you want to use this stack without a license then remove the license-call containers from the docker-compose file

To initialise the folders that Logstash will use to copy over its configuration
with any test logs.

```bash
./initialise.sh
```

Then put any test logstash configuration in the /logstash/config folder, logs
to ingest in the /logstash/logs folder and optionally logstash patterns in the
patterns folder and elasticsearch mapping templates in templates.

## Running

Spin up the stack with:

```bash
docker-compose up
```

Once up:

   * Elasticsearch will be available on localhost:9200 and localhost:8200
   * Kibana will be available on localhost:5601
   * Kopf will be on localhost:8080
   * Mailhog will have its web UI on localhost:8025 and the smtp service will be on port 1025
   * Marvel, Sense and Timelion will be available from the Kibana plugins menu option
   

