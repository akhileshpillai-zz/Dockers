FROM akhileshpillai/flume160:latest
MAINTAINER Akhilesh Pillai akhileshpillai@gmail.com

ADD twitter-flume.conf /opt/flume/conf/svda-twitter-flume.conf

RUN mkdir /commonlibs
RUN wget -qO- http://mirror.symnds.com/software/Apache/hadoop/common/hadoop-2.7.0/hadoop-2.7.0.tar.gz \
  | tar zxvf - -C /commonlibs --strip 1

RUN cp /commonlibs/share/hadoop/hdfs/hadoop-hdfs-2.7.0.jar /opt/flume/lib
RUN cp /commonlibs/share/hadoop/common/hadoop-common-2.7.0.jar /opt/flume/lib/
RUN cp /commonlibs/share/hadoop/common/lib/commons-configuration-1.6.jar /opt/flume/lib/
RUN cp /commonlibs/share/hadoop/common/lib/commons-httpclient-3.1.jar /opt/flume/lib/
RUN cp /commonlibs/share/hadoop/common/lib/jets3t-0.9.0.jar /opt/flume/lib/
RUN cp /commonlibs/share/hadoop/common/lib/hadoop-auth-2.7.0.jar /opt/flume/lib/
RUN cp /commonlibs/share/hadoop/common/lib/hadoop-annotations-2.7.0.jar /opt/flume/lib/
RUN cp /commonlibs/share/hadoop/hdfs/lib/htrace-core-3.1.0-incubating.jar /opt/flume/lib/
RUN cp /commonlibs/share/hadoop/common/lib/commons-io-2.4.jar /opt/flume/lib/
RUN rm /opt/flume/lib/commons-io-2.1.jar

ENV FLUME_AGENT_NAME TwitterAgent
ENV FLUME_CONF_FILE  /opt/flume/conf/svda-twitter-flume.conf
ENV FLUME_CONF_DIR  /opt/flume/conf
