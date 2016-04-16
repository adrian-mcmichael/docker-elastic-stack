# docker-elastic-stack

This is a work in progress.

## Requirements

Install the Docker toolbox at at least version 1.11.0 

## What works

The following works:

* Spins up a two node elasticsearch (ports 9200 and 8200 respectively)
* Installs marvel
* Spins up Kopf as a standalone server on port 8080
* Mounts elasticsearch data containers

Known issues:

* File permissions on Kibana mean that it isn't starting up

Todo:

* Add the logstash component

## Running

```bash
docker-compose up
```
