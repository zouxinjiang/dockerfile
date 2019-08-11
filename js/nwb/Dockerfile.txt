FROM centos:latest

MAINTAINER 1205561952@qq.com

ARG Node=node-v10.16.2-linux-x64

LABEL ImageName="react nwb"

USER root
WORKDIR /root

ENV NODEROOT=/root/${Node}
ENV PATH=$PATH:$NODEROOT/bin

RUN yum install -y wget bzip2; \
    wget https://nodejs.org/dist/v10.16.2/${Node}.tar.xz; \
    xz -d ${Node}.tar.xz; \
    tar -xvf ${Node}.tar; \
    rm -rf ${Node}.tar; \
    npm install -g cnpm --registry=https://registry.npm.taobao.org; \
    cnpm install -g nwb; \
    mkdir /react; 

VOLUME ["/react"]

EXPOSE 22 3000 3001 3002 80 443

CMD ["/bin/bash"]

