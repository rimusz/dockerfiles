FROM quay.io/rimusz/alpine-base:latest
MAINTAINER Rimas Mocevicius rmocius@gmail.com

ENV NPM_CONFIG_GLOBALCONFIG /etc/npmrc
COPY npmrc /etc/npmrc

RUN apk-install \
    --virtual docker-nodejs \
    --no-progress \
    --force \
    nodejs && \
    npm -g install npm && \
    npm cache clean
