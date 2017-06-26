# use ubuntu 17.04
FROM hub.c.163.com/library/ubuntu:yakkety

# tsing hua deb source
RUN echo '# Tsinghua deb source \n\
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ yakkety main restricted universe multiverse  \n\
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ yakkety-updates main restricted universe multiverse \n\
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ yakkety-backports main restricted universe multiverse \n\
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ yakkety-security main restricted universe multiverse'  >> /etc/apt/sources.list

RUN apt-get update
RUN apt-get install vim -y

# install gcc
RUN apt-get install build-essential -y; exit 0
RUN apt-get install gcc-5 -y
RUN apt-get install gcc-4.8 -y
RUN apt-get install libnuma-dev -y

RUN apt-get update
RUN apt-get install wget -y

RUN apt-get install perl -y
RUN apt-get install libaio1 libaio-dev -y


RUN useradd terark


# mysql-on-terarkdb-5.4-bmi2-1, If your CPU support BMI2, please un-comment the following 6 lines and comment out mysql-on-terarkdb-4.8-bmi2-0
#RUN cd /home && wget http://terark-downloads.oss-cn-qingdao.aliyuncs.com/mysql_rocksdb/r5.6.35/mysql-on-terarkdb-Linux-x86_64-g%2B%2B-5.4-bmi2-1.tar.xz
#RUN cd /home && tar -xvf mysql-on-terarkdb-Linux-x86_64-g++-5.4-bmi2-1.tar.xz
#RUN cd /home && rm -rf mysql-on-terarkdb-Linux-x86_64-g++-5.4-bmi2-1.tar.xz
#RUN cd /home/mysql-on-terarkdb-5.4-bmi2-1 && chown -R terark.terark .
#RUN echo 'rocksdb_commit_in_the_middle=1' >> /home/mysql-on-terarkdb-5.4-bmi2-1/my.cnf
#RUN cd /home/mysql-on-terarkdb-5.4-bmi2-1 && ./init.sh

# mysql-on-terarkdb-4.8-bmi2-0
RUN cd /home && wget http://terark-downloads.oss-cn-qingdao.aliyuncs.com/mysql_rocksdb/r5.6.35/mysql-on-terarkdb-Linux-x86_64-g%2B%2B-4.8-bmi2-0.tar.xz
RUN cd /home && tar -xvf mysql-on-terarkdb-Linux-x86_64-g++-4.8-bmi2-0.tar.xz
RUN cd /home && rm -rf mysql-on-terarkdb-Linux-x86_64-g++-4.8-bmi2-0.tar.xz
RUN cd /home/mysql-on-terarkdb-4.8-bmi2-0 && chown -R terark.terark .
RUN echo 'rocksdb_commit_in_the_middle=1' >> /home/mysql-on-terarkdb-4.8-bmi2-0/my.cnf
RUN cd /home/mysql-on-terarkdb-4.8-bmi2-0 && ./init.sh



# extra tools
RUN apt-get install libreadline6 libreadline6-dev -y
RUN apt-get install openjdk-8-jre -y; exit 0

RUN apt-get install libreadline6 libreadline6-dev -y
RUN apt-get install git -y; exit 0
RUN apt-get install python -y; exit 0
