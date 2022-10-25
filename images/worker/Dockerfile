FROM alpine:3.16
USER root
COPY ssh /root/.ssh
COPY keychain /root/keychain
WORKDIR /root

RUN apk update && apk upgrade && apk add \
        git \
        npm \
        openrc \
        openssh \
        openjdk17 \
        docker-cli

# touch softlevel because system was initialized without openrc
RUN rc-status && touch /run/openrc/softlevel
RUN rc-service sshd start

# Login to docker registry using credentils from keychain/docker (format == registry_name:access_token)
RUN cut -d: -f2 keychain/docker | docker login -u "$(cut -d: -f1 keychain/docker)" --password-stdin
CMD ["/usr/sbin/sshd", "-D"]
