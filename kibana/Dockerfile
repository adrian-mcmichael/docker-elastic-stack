FROM kibana:4.6

COPY kibana.yml /opt/kibana/config

RUN chown -R kibana:kibana /opt/kibana/
RUN chown kibana:kibana /opt/kibana/optimize

RUN gosu kibana kibana plugin --install elasticsearch/marvel/2.4.1
RUN gosu kibana kibana plugin --install elastic/sense
RUN gosu kibana kibana plugin --install kibana/timelion
RUN gosu kibana kibana plugin --install prelert_swimlane_vis -u https://github.com/prelert/kibana-swimlane-vis/archive/v0.1.0.tar.gz

HEALTHCHECK --interval=30s --timeout=30s \
  CMD curl -f http://localhost:5601/ || exit 1

CMD ["kibana"]
