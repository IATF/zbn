FROM daocloud.io/library/centos:centos8
LABEL MAINTAINER=z-3zh
RUN yum -y update
RUN yum install -y python38-devel mysql-devel gcc gcc-c++ automake autoconf libtool openssl-devel bzip2-devel libffi-devel git wget make python38.x86_64
WORKDIR /root
RUN git clone https://github.com/zbnio/zbn.git
WORKDIR /root/zbn
COPY ./supervisord.conf /etc/supervisord.conf
COPY ./entrypoint.sh ./
COPY ./config.ini ./config.ini
RUN pip3 install --upgrade pip
RUN pip3 install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple
WORKDIR /root/zbn
RUN chmod +x entrypoint.sh
CMD ["./entrypoint.sh"]

