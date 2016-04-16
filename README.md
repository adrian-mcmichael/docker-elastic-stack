# docker-elastic-stack

This is a work in progress.

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
 
