FROM alpine:3.12

# Default to UTF-8 file.encoding
ENV LANG C.UTF-8

ENV JAVA_HOME /usr/lib/jvm/java-1.8-openjdk
ENV PATH $PATH:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin

ENV JAVA_ALPINE_VERSION 8.242.08-r2

RUN set -x  \
    && apk update   \
    && apk add --no-cache   \
    curl    \
    net-tools   \
    bash \
    openjdk8="$JAVA_ALPINE_VERSION" \
    krb5    \
    openssl \
    && wget https://archive.apache.org/dist/kafka/0.10.1.0/kafka_2.10-0.10.1.0.tgz \
    && tar -xvf kafka_2.10-0.10.1.0.tgz  -C /opt \
    && rm -rf  kafka_2.10-0.10.1.0.tgz

