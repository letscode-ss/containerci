FROM gliderlabs/alpine:latest
MAINTAINER Shivendra Sharma "shivendra.sharma@sapient.com"
RUN apk add --no-cache openjdk8 curl jq bash openssh maven apache-ant tree

ENV USER=jenkins
ENV UID=1000
ENV GID=1000

ADD https://github.com/mikefarah/yq/releases/download/3.2.1/yq_linux_amd64 ./

RUN apk add --no-cache libxml2 libxml2-utils unzip git zip sshpass ssl_client && \
    mv yq_linux_amd64 /usr/local/bin/yq  && \
    chmod +x /usr/local/bin/yq && \
    addgroup --gid "$GID" -S "${USER}" && adduser --uid "$UID" -S "${USER}" -G "${USER}"

# Tell docker that all future commands should run as the appuser user
USER "${UID}"


CMD ["/bin/sh"]

