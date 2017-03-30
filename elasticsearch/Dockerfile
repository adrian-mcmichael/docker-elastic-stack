FROM elasticsearch:2.4.1

RUN apt-get update && apt-get install -y curl

COPY elasticsearch.yml /usr/share/elasticsearch/config

RUN /usr/share/elasticsearch/bin/plugin install license
RUN /usr/share/elasticsearch/bin/plugin install watcher
RUN /usr/share/elasticsearch/bin/plugin install marvel-agent

HEALTHCHECK --interval=30s --timeout=30s \
  CMD curl -f http://localhost:9200/ || exit 1
