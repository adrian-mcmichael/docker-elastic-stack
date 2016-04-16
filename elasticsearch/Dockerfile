FROM elasticsearch:2.3.1

COPY ../config/elasticsearch /usr/share/elasticsearch

WORKDIR /usr/share/elasticsearch/bin

RUN plugin install license
RUN plugin install marvel-agent
