FROM openjdk:8-jre-alpine

MAINTAINER Mihai CAZACU (cazacugmihai@gmail.com)

ARG HADOOP_VERSION=2.8.1
ARG HADOOP_HOME=/usr/lib/hadoop

RUN apk add --no-cache bash && \
	wget http://apache.javapipe.com/hadoop/common/hadoop-${HADOOP_VERSION}/hadoop-${HADOOP_VERSION}.tar.gz -O - | tar xz && \
	mv hadoop-${HADOOP_VERSION} ${HADOOP_HOME} && \
	echo "export JAVA_HOME=${JAVA_HOME}" > /etc/profile.d/java.sh && \
	echo "export HADOOP_HOME=${HADOOP_HOME}" > /etc/profile.d/hadoop.sh

ENV HADOOP_HOME=${HADOOP_HOME} \
	PATH=$PATH:$HADOOP_HOME/bin:$HADOOP_HOME/sbin

CMD bash