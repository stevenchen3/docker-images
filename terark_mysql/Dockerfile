# use ubuntu 17.04
FROM hub.c.163.com/library/ubuntu:yakkety

RUN apt-get update
RUN apt-get install vim -y

# install gcc
RUN apt-get install build-essential -y; exit 0
RUN apt-get install gcc-5 -y
RUN apt-get install libnuma-dev -y

# tsing hua deb source
RUN echo '# Tsinghua deb source \n\
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ yakkety main restricted universe multiverse  \n\
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ yakkety-updates main restricted universe multiverse \n\
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ yakkety-backports main restricted universe multiverse \n\
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ yakkety-security main restricted universe multiverse'  >> /etc/apt/sources.list


RUN apt-get update
RUN apt-get install wget -y

RUN apt-get install perl -y
RUN apt-get install libaio1 libaio-dev -y

RUN cd /home && wget http://terark-downloads.oss-cn-qingdao.aliyuncs.com/mysql_rocksdb/r5.6.35/mysql-on-terarkdb-Linux-x86_64-g%2B%2B-5.4-bmi2-1.tar.xz
RUN cd /home && tar -xvf mysql-on-terarkdb-Linux-x86_64-g++-5.4-bmi2-1.tar.xz
RUN useradd terark && cd /home/mysql-on-terarkdb && chown -R terark.terark .
RUN cd /home/mysql-on-terarkdb && ./init.sh

RUN apt-get install libreadline6 libreadline6-dev -y
RUN apt-get install git -y; exit 0
