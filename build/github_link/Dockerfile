# base on openjdk_8, not compatible with openjdk_11
FROM openjdk:8u242

MAINTAINER bosco<boscoliao01@gmail.com>

# set label
LABEL version=1.1.0.x \
      author="BoscoL"

# set environment
ENV SEATA_USER="seata" \
    TIME_ZONE="Asia/Shanghai"

ARG SEATA_VERSION=1.1.0.x

WORKDIR /seata-server

RUN set -x \
    && wget https://github.com/BoscoL/seata/releases/download/v${SEATA_VERSION}/seata-server-${SEATA_VERSION}.tar.gz -P /seata-server \
    && tar -xzvf /seata-server/seata-server-${SEATA_VERSION}.tar.gz \
	&& mv /seata-server/seata/* ./ \
    && rm -rf /seata-server/seata /seata-server/seata-server-${SEATA_VERSION}.tar.gz \
    && ln -snf /usr/share/zoneinfo/$TIME_ZONE /etc/localtime && echo '$TIME_ZONE' > /etc/timezone

# 设置额外参数
ENV EXTRA_JVM_ARGUMENTS="-XX:MaxDirectMemorySize=1024M"

ENTRYPOINT ["sh","/seata-server/bin/seata-server.sh"]

EXPOSE 8091
