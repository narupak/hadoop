FROM ubuntu:18:04

RUN apt update 
RUN apt-get install openjdk-8-jdk -y 
RUN apt install wget
RUN wget http://mirror.intergrid.com.au/apache/hadoop/common/hadoop-3.2.0/hadoop-3.2.0.tar.gz
RUN mkdir hadoop
RUN tar -xvzf hadoop-3.2.0.tar.gz -C hadoop
RUN cd hadoop/hadoop-3.2.0/
VOLUME [ "./hadoop-env.sh:/hadoop/hadoop-3.2.0/etc/hadoop/core-site.xml" ]
VOLUME [ "./node/core-site.xml:/hadoop/hadoop-3.2.0/etc/hadoop/core-site.xml" ]
VOLUME [ "./node/hdfs-site.xml:/hadoop/hadoop-3.2.0/etc/hadoop/hdfs-site.xml" ]
VOLUME [ "./node/mapred-site.xml:/hadoop/hadoop-3.2.0/etc/hadoop/mapred-site.xml" ]
VOLUME [ "./node/yarn-site.xml:/hadoop/hadoop-3.2.0/etc/hadoop/yarn-site.xml" ]
RUN bin/hdfs namenode -format
RUN sbin/start-dfs.sh
RUN sbin/start-yarn.sh


VOLUME [ "./.basher:/etc/bash.bashrc" ]