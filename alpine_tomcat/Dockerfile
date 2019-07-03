FROM alpine:3.9
MAINTAINER d.ermizin <kernel218@gmail.com>
ENV CATALINA_HOME /usr/local/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH

RUN apk add -q openjdk8
RUN mkdir -p "$CATALINA_HOME"
WORKDIR $CATALINA_HOME

ENV TOMCAT_MAJOR 8
ENV TOMCAT_VERSION 8.5.42
ENV TOMCAT_TGZ_URL https://www.apache.org/dist/tomcat/tomcat-$TOMCAT_MAJOR/v$TOMCAT_VERSION/bin/apache-tomcat-$TOMCAT_VERSION.tar.gz

RUN wget -q "$TOMCAT_TGZ_URL" -O tomcat.tar.gz \
    && tar -xf tomcat.tar.gz --strip-components=1 \
    && rm bin/*.bat \
    && rm tomcat.tar.gz* \
    && rm -fr $CATALINA_HOME/webapps/*
COPY --from=lab7_maven:latest /maven_build/target/hello-*.war $CATALINA_HOME/webapps/hello.war

CMD ["catalina.sh", "run"]
