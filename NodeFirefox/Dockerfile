FROM selenium/node-base:2.44.0
MAINTAINER Selenium <selenium-developers@googlegroups.com>

USER root

#=========
# Firefox
#=========
ENV FIREFOX_VERSION 34.0.5
RUN apt-get update -qqy \
  && apt-get -qqy --no-install-recommends install \
    bzip2 \
  && rm -rf /var/lib/apt/lists/* \
  && wget --no-verbose -O /tmp/firefox.tar.bz2 ftp.mozilla.org/pub/mozilla.org/firefox/releases/$FIREFOX_VERSION/linux-x86_64/en-US/firefox-$FIREFOX_VERSION.tar.bz2 \
  && tar -xjvf /tmp/firefox.tar.bz2 -C /opt \
  && ln -sf /opt/firefox/firefox /usr/bin/firefox \
  && rm /tmp/firefox.tar.bz2
#RUN apt-get update -qqy \
#  && apt-get -qqy --no-install-recommends install \
#    firefox \
#  && rm -rf /var/lib/apt/lists/*

#========================
# Selenium Configuration
#========================
COPY config.json /opt/selenium/config.json

USER seluser
