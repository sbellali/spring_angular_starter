FROM maven:latest AS package
RUN apt-get update -y && \
    apt-get install -y inotify-tools && \
    mkdir /usr/app  && \
    mkdir /usr/jar
ENV TEST_SKIP "true"
CMD ["/usr/app/scripts/package"]


FROM eclipse-temurin:17 AS developement
RUN apt-get update -y && \
    apt-get install -y inotify-tools && \
    mkdir /usr/scripts && \
    mkdir /usr/jar
COPY scripts/run /usr/scripts/run
CMD ["/usr/scripts/run"]