FROM python:alpine3.12
RUN apk add gcc libc-dev openssl-dev libffi-dev && \
    pip install Flask prometheus_client pyjks pyOpenSSL

ENTRYPOINT ['python']
