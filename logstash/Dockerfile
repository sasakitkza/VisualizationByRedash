FROM docker.elastic.co/logstash/logstash:7.13.3

RUN rm -f /usr/share/logstash/pipeline/logstash.conf
ADD pipeline/ /usr/share/logstash/pipeline/
ADD config/ /usr/share/logstash/config/

RUN bin/logstash-plugin install --version=3.1.5 logstash-output-mongodb