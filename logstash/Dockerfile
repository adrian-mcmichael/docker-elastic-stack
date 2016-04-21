FROM logstash:2.3.1

COPY ./config/ /config-dir
COPY ./templates/ /templates
COPY ./patterns/ /patterns
COPY ./logs/ /logs

CMD ["logstash", "-f", "/config-dir/"]
