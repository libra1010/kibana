FROM docker.elastic.co/kibana/kibana:6.2.3
MAINTAINER libra@ljing.wang
COPY x-pack-core-6.2.3.jar /usr/share/elasticsearch/plugins/x-pack/x-pack-core/x-pack-core-6.2.3.jar

RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
RUN arch="$(dpkg --print-architecture)" \\\\
    && set -x \\\\
    && curl -o /usr/local/bin/gosu -fSL "https://github.com/tianon/gosu/releases/download/1.7/gosu-$arch" \\\\
    && curl -o /usr/local/bin/gosu.asc -fSL "https://github.com/tianon/gosu/releases/download/1.7/gosu-$arch.asc" \\\\
    && gpg --verify /usr/local/bin/gosu.asc \\\\
    && rm /usr/local/bin/gosu.asc \\\\
    && chmod +x /usr/local/bin/gosu


RUN  gosu yum install net-tools -y 
RUN  gosu yum install vim -y