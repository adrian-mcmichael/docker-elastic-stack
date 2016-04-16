FROM kibana:4.5

COPY ../config/kibana /opt/kibana/config

RUN gosu kibana kibana plugin plugin --install elasticsearch/marvel/2.3.1
RUN gosu kibana kibana pluginplugin --install elastic/sense
RUN gosu kibana kibana plugin plugin --install kibana/timelion

RUN chmod o+w /opt/kibana/optimize/.babelcache.json
RUN chown -R kibana:kibana /opt/kibana
