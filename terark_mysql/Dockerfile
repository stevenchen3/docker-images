# use ubuntu 17.04
FROM hub.c.163.com/library/ubuntu:yakkety

# tsing hua deb source
RUN echo '# Tsinghua deb source \n\
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ yakkety main restricted universe multiverse  \n\
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ yakkety-updates main restricted universe multiverse \n\
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ yakkety-backports main restricted universe multiverse \n\
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ yakkety-security main restricted universe multiverse'  >> /etc/apt/sources.list

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    gcc-4.8 \
    gcc-5 \
    git \
    libaio1 \
    libaio-dev \
    libnuma-dev \
    libreadline6 \
    libreadline6-dev \
    perl \
    python \
    vim \
    wget && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN useradd terark

ENV TERARK_DB_URL_BASE http://terark-downloads.oss-cn-qingdao.aliyuncs.com/mysql_rocksdb/r5.6.35
# mysql-on-terarkdb-5.4-bmi2-1, If your CPU support BMI2, please un-comment the following 6 lines
# and comment out mysql-on-terarkdb-4.8-bmi2-0
#ENV TERARK_DB_URL ${TERARK_DB_URL_BASE}/mysql-on-terarkdb-Linux-x86_64-g%2B%2B-5.4-bmi2-1.tar.xz
#RUN cd /home && \
#    wget ${TERARK_DB_URL} && \
#    tar -xvf mysql-on-terarkdb-Linux-x86_64-g++-5.4-bmi2-1.tar.xz && \
#    rm -rf mysql-on-terarkdb-Linux-x86_64-g++-5.4-bmi2-1.tar.xz && \
#    cd /home/mysql-on-terarkdb-5.4-bmi2-1 && \
#    chown -R terark.terark . && \
#    echo 'rocksdb_commit_in_the_middle=1' >> /home/mysql-on-terarkdb-5.4-bmi2-1/my.cnf && \
#    cd /home/mysql-on-terarkdb-5.4-bmi2-1 && \
#    ./init.sh

# mysql-on-terarkdb-4.8-bmi2-0
ENV TERARK_DB_URL ${TERARK_DB_URL_BASE}/mysql-on-terarkdb-Linux-x86_64-g%2B%2B-4.8-bmi2-0.tar.xz
RUN cd /home && \
    wget ${TERARK_DB_URL} && \
    tar -xvf mysql-on-terarkdb-Linux-x86_64-g++-4.8-bmi2-0.tar.xz && \
    rm -rf mysql-on-terarkdb-Linux-x86_64-g++-4.8-bmi2-0.tar.xz && \
    cd /home/mysql-on-terarkdb-4.8-bmi2-0 && \
    chown -R terark.terark . && \
    echo 'rocksdb_commit_in_the_middle=1' >> /home/mysql-on-terarkdb-4.8-bmi2-0/my.cnf && \
    cd /home/mysql-on-terarkdb-4.8-bmi2-0 && \
    ./init.sh
