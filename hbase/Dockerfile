FROM openjdk:8-jre-alpine

MAINTAINER Mihai CAZACU (cazacugmihai@gmail.com)

ARG HBASE_VERSION=1.3.1
ARG HBASE_HOME=/usr/lib/hbase

RUN apk add --no-cache bash && \
	wget http://apache.javapipe.com/hbase/${HBASE_VERSION}/hbase-${HBASE_VERSION}-bin.tar.gz -O - | tar xz && \
	mv hbase-${HBASE_VERSION} ${HBASE_HOME} && \
	echo "export JAVA_HOME=${JAVA_HOME}" > /etc/profile.d/java.sh && \
	echo "export HBASE_HOME=${HBASE_HOME}" > /etc/profile.d/hbase.sh

ENV HBASE_HOME=${HBASE_HOME} \
	PATH=$PATH:$HBASE_HOME/bin

# WebUI
EXPOSE 16010

CMD start-hbase.sh && \
	tail -f /dev/null