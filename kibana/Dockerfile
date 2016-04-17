FROM kibana:4.5.0

COPY kibana.yml /opt/kibana/config

RUN chown -R kibana:kibana /opt/kibana/
RUN chown kibana:kibana /opt/kibana/optimize

RUN gosu kibana kibana plugin --install elasticsearch/marvel/2.3.1
RUN gosu kibana kibana plugin --install elastic/sense
RUN gosu kibana kibana plugin --install kibana/timelion
