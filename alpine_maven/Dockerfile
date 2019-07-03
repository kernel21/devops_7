FROM alpine:3.9
MAINTAINER d.ermizin <kernel218@gmail.com>
RUN apk update -q && apk add -q git \
    maven \
    openjdk8 \
    maven
#WORKDIR maven_build/
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git /maven_build
RUN cd /maven_build && mvn -q package
