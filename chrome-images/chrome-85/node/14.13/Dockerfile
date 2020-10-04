FROM centos:centos7

COPY google-chrome.repo /etc/yum.repos.d/google-chrome.repo
RUN yum install -y jq yq zip unzip curl wget openssl file google-chrome-stable-85.0.4183.121-1.x86_64 bzip2 git java-1.8.0-openjdk.x86_64
# Default to UTF-8 file.encoding
ENV LANG C.UTF-8

RUN wget -q -O /tmp/node.tar.gz https://nodejs.org/dist/latest/node-v14.13.0-linux-x64.tar.gz   \
    && tar -xvf /tmp/node.tar.gz -C /opt/   \
    && ln -s /opt/node-v14.13.0-linux-x64/bin/npm /usr/bin/npm   \
    && ln -s /opt/node-v14.13.0-linux-x64/bin/node /usr/bin/node  \
    && rm -rf  /tmp/node.tar.gz

ARG CHROME_DRIVER_VERSION=86.0.4240.22
RUN wget -q -O /tmp/chromedriver.zip https://chromedriver.storage.googleapis.com/$CHROME_DRIVER_VERSION/chromedriver_linux64.zip \
	&& unzip /tmp/chromedriver.zip -d /opt \
	&& rm /tmp/chromedriver.zip \
	&& mv /opt/chromedriver /opt/chromedriver-$CHROME_DRIVER_VERSION \
	&& chmod 755 /opt/chromedriver-$CHROME_DRIVER_VERSION \
	&& ln -s /opt/chromedriver-$CHROME_DRIVER_VERSION /usr/bin/chromedriver \
    && rm -rf  /tmp/chromedriver.zip