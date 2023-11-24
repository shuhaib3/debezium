FROM quay.io/strimzi/kafka:0.35.1-kafka-3.4.0
USER root:root
ENV KAFKA_HOME=/opt/kafka

ARG DEBEZIUM_VERSION=2.4.1.Final
ARG CONNECTOR_NAME=debezium-connector-mongodb

RUN mkdir -p /opt/kafka/plugins

RUN curl https://repo1.maven.org/maven2/io/debezium/debezium-connector-mongodb/${DEBEZIUM_VERSION}/${CONNECTOR_NAME}-${DEBEZIUM_VERSION}-plugin.tar.gz -o /opt/kafka/plugins/${CONNECTOR_NAME}-${DEBEZIUM_VERSION}-plugin.tar.gz \
    && tar -xzvf /opt/kafka/plugins/${CONNECTOR_NAME}-${DEBEZIUM_VERSION}-plugin.tar.gz -C /opt/kafka/plugins/ \
    && rm /opt/kafka/plugins/${CONNECTOR_NAME}-${DEBEZIUM_VERSION}-plugin.tar.gz

USER 1001