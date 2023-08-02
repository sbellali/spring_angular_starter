FROM maven:latest AS package
RUN apt-get update -y && \
    apt-get install -y inotify-tools && \
    mkdir /scripts && \
    mkdir /app  && \
    mkdir /jar
COPY scripts/package /scripts/package
CMD ["/scripts/package"]


FROM eclipse-temurin:17 AS developement
RUN apt-get update -y && \
    apt-get install -y inotify-tools && \
    mkdir /scripts && \
    mkdir /jar
COPY scripts/run /scripts/run
CMD ["/scripts/run"]