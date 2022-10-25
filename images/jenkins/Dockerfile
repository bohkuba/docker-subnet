FROM jenkins/jenkins:alpine
USER root
COPY ssh /root/.ssh
WORKDIR /var/jenkins_home

RUN apk update && apk upgrade && apk add \
        docker-cli
