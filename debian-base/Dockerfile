FROM debian:stable-slim

RUN apt update
RUN apt install python3.7 g++ build-essential curl git rename openssl jq unzip -y \
    && curl -SLO "https://github.com/mikefarah/yq/releases/download/3.3.0/yq_linux_amd64" --insecure \
    && mv yq_linux_amd64  /usr/local/bin/yq && chmod +x  /usr/local/bin/yq

