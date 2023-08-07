ARG JAVA_VERSION_TAG=11

FROM maven:latest AS package
ARG UID=1000
ARG GID=1000
RUN apt-get update -y && \
    apt-get install -y inotify-tools && \
    mkdir /usr/app /usr/jar /usr/.m2
RUN chown -R $UID:$GID /usr
ENV TEST_SKIP "true"
CMD ["/usr/app/scripts/package"]

FROM eclipse-temurin:$JAVA_VERSION_TAG AS developement
ARG UID=1000
ARG GID=1000
RUN apt-get update -y && \
    apt-get install -y inotify-tools && \
    mkdir /usr/scripts /usr/jar 
RUN chown -R $UID:$GID /usr
COPY scripts/run /usr/scripts/run
CMD ["/usr/scripts/run"]