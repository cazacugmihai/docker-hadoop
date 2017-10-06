FROM cazacugmihai/hadoop

MAINTAINER Mihai CAZACU (cazacugmihai@gmail.com)

COPY conf/ssh/sshd_config /etc/ssh/sshd_config
COPY conf/ssh/config /root/.ssh/config

RUN apk add --no-cache openssh rsync && \
	echo -e 'y\n' | ssh-keygen -q -N "" -t rsa -f ~/.ssh/id_rsa && \
	cp ~/.ssh/id_rsa.pub ~/.ssh/authorized_keys && \
	chmod 700 ~/.ssh && \
	chmod 600 ~/.ssh/authorized_keys && \
	chmod 600 ~/.ssh/config

# echo -e 'y\n' | ssh-keygen -q -N "" -t dsa -f /etc/ssh/ssh_host_dsa_key && \
# echo -e 'y\n' | ssh-keygen -q -N "" -t rsa -f /etc/ssh/ssh_host_rsa_key && \
# echo -e 'y\n' | ssh-keygen -q -N "" -t ecdsa -f /etc/ssh/ssh_host_ecdsa_key && \
# echo -e 'y\n' | ssh-keygen -q -N "" -t ed25519 -f /etc/ssh/ssh_host_ed25519_key && \
# eval "$(ssh-agent -s)" && \
# ssh-add
# ssh-keygen -A && \
# NoHostAuthenticationForLocalhost

# hadoop

COPY conf/hadoop/core-site.xml $HADOOP_HOME/etc/hadoop/
COPY conf/hadoop/hdfs-site.xml $HADOOP_HOME/etc/hadoop/

RUN sed -i "s!^export JAVA_HOME.*!export JAVA_HOME=$JAVA_HOME!" $HADOOP_HOME/etc/hadoop/hadoop-env.sh

# dor debug: /usr/sbin/sshd -d
CMD /usr/sbin/sshd -D