FROM amazonlinux:2018.03

RUN yum upgrade -y \
    && yum -y install python36 python36-virtualenv python36-pip zip \
    && rm -rf /var/cache/yum/* \
    && yum clean all
RUN python3 -m pip install --upgrade pip
RUN python3 -m pip install numpy
