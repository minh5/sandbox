FROM ubuntu:trusty

MAINTAINER minh mai
USER root

# download and configure Kudu
RUN apt-get update && apt-get -y install wget curl ntp && \
    cd /etc/apt/sources.list.d && \
    wget -qO - http://archive.cloudera.com/beta/kudu/ubuntu/trusty/amd64/kudu/archive.key | sudo apt-key add - && \
    wget http://archive.cloudera.com/beta/kudu/ubuntu/trusty/amd64/kudu/cloudera.list && \
    apt-get update && \
    apt-get -y dist-upgrade && \
    apt-get -y install kudu kudu-master kudu-tserver libkuduclient0 libkuduclient-dev

VOLUME /var/lib/kudu/master /var/lib/kudu/tserver
EXPOSE 8050 8051 7050 7051