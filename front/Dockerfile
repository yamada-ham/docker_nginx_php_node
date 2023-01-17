FROM ubuntu:22.04

RUN apt-get update -y

RUN apt-get install -y curl vim lsof

RUN curl -sL https://deb.nodesource.com/setup_18.x | bash - && \
    apt-get install -y nodejs
