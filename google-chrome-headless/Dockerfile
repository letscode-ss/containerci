# Source @ https://github.com/femtopixel/docker-google-lighthouse

FROM femtopixel/google-chrome-headless

ARG VERSION=v6.3.0

LABEL maintainer="Jay MOULIN <https://jaymoulin.me/femtopixel/docker-google-lighthouse> <http://twitter.com/MoulinJay>"
LABEL version="${VERSION}"

USER root

# Install deps + add Chrome Stable + purge all the things
RUN rm -rf /var/lib/apt/lists/* && \
  apt-get update && \
  apt-get remove gnupg -y && apt-get install --reinstall gnupg2 dirmngr --allow-unauthenticated -y && \
  apt-get autoclean && apt-get update && apt-get install -y apt-transport-https ca-certificates curl gnupg --no-install-recommends && \
  curl -sSL https://deb.nodesource.com/setup_13.x | bash - && \
  apt-get install -y nodejs --no-install-recommends && \
  npm --global install npm && \
  npm --global install yarn && \
  apt-get purge --auto-remove -y curl gnupg && \
  rm -rf /var/lib/apt/lists/* && \
  npm install --global lighthouse && \
  mkdir -p /opt/chrome/reports && chmod 777 /opt/ && chown -R chrome:chrome /opt/chrome

# some place we can mount and view lighthouse reports
WORKDIR /opt/chrome/reports

COPY entrypoint.sh /usr/bin/entrypoint

# Run Chrome non-privileged
USER chrome

ENV CHROME_FLAGS="--headless --disable-gpu --no-sandbox"


# Drop to cli
ENTRYPOINT ["entrypoint"]
