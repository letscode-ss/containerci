FROM alpine:3.12

MAINTAINER letsmailshiv@gmail.com

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
    busybox-extras
