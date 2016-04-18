FROM elasticsearch:2.3.1

COPY elasticsearch.yml /usr/share/elasticsearch/config

WORKDIR /usr/share/elasticsearch/bin

RUN plugin install license
RUN plugin install marvel-agent
