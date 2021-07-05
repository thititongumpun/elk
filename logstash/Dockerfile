#ARG ELK_VERSION

# https://www.docker.elastic.co/
#FROM docker.elastic.co/logstash/logstash:${ELK_VERSION}

# Add your logstash plugins setup here
# Example: RUN logstash-plugin install logstash-filter-json


FROM docker.elastic.co/logstash/logstash:6.6.0

# install dependency
RUN /usr/share/logstash/bin/logstash-plugin install logstash-input-jdbc
RUN /usr/share/logstash/bin/logstash-plugin install logstash-filter-aggregate
RUN /usr/share/logstash/bin/logstash-plugin install logstash-filter-jdbc_streaming
RUN /usr/share/logstash/bin/logstash-plugin install logstash-filter-mutate
#RUN /usr/share/logstash/bin/logstash-plugin install x-pack
# copy lib database jdbc jars
COPY ./mysql-connector-java-8.0.11.jar /usr/share/logstash/logstash-core/lib/jars/mysql-connector-java.jar
