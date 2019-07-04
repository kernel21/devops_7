FROM alpine:latest
MAINTAINER d.ermizin <kernel218@gmail.com>
RUN apk update -q && apk add -q git \
    maven \
    openjdk8 \
    && rm -rf /var/cache/apk/*
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git /maven_build
WORKDIR /maven_build
RUN mvn -q package
