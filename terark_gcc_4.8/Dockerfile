# use ubuntu 17.04
FROM hub.c.163.com/library/ubuntu:yakkety

RUN apt-get update
RUN apt-get install vim -y

# install gcc
RUN apt-get install build-essential -y; exit 0
RUN apt-get install gcc-4.8 -y

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




