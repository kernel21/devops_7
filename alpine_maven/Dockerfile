FROM alpine:3.9
MAINTAINER d.ermizin <kernel218@gmail.com>
RUN apk update && apk add git \
    maven \
    openjdk8 \
    maven
RUN mkdir maven_build  && git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git maven_build
RUN cd maven_build && mvn -q package

