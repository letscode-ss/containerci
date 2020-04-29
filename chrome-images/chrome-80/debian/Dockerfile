FROM debian:stable-slim

RUN apt update
RUN apt install python3.7 g++ build-essential curl git rename openssl jq unzip wget -y \
    && curl -SLO "https://github.com/mikefarah/yq/releases/download/3.3.0/yq_linux_amd64" --insecure \
    && mv yq_linux_amd64  /usr/local/bin/yq && chmod +x  /usr/local/bin/yq

RUN wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb && \
    apt install ./google-chrome-stable_current_amd64.deb  -y && \
    rm -rf google-chrome-stable_current_amd64.deb


# ChromeDriver

ARG CHROME_DRIVER_VERSION=81.0.4044.20
RUN wget -q -O /tmp/chromedriver.zip https://chromedriver.storage.googleapis.com/$CHROME_DRIVER_VERSION/chromedriver_linux64.zip \
	&& unzip /tmp/chromedriver.zip -d /opt \
	&& rm /tmp/chromedriver.zip \
	&& mv /opt/chromedriver /opt/chromedriver-$CHROME_DRIVER_VERSION \
	&& chmod 755 /opt/chromedriver-$CHROME_DRIVER_VERSION \
	&& ln -s /opt/chromedriver-$CHROME_DRIVER_VERSION /usr/bin/chromedriver
