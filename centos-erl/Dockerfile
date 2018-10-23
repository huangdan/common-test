FROM centos:7

RUN yum update -y \
    && yum install -y vim git make gcc wget epel-release \
    && wget https://packages.erlang-solutions.com/erlang-solutions-1.0-1.noarch.rpm \
    && rpm -Uvh erlang-solutions-1.0-1.noarch.rpm \
    && rpm --import https://packages.erlang-solutions.com/rpm/erlang_solutions.asc

RUN echo '[erlang-solutions]'  >> /etc/yum.repos.d/CentOS-Base.repo \
    && echo 'name=CentOS $releasever - $basearch - Erlang Solutions'  >> /etc/yum.repos.d/CentOS-Base.repo \
    && echo 'baseurl=https://packages.erlang-solutions.com/rpm/centos/$releasever/$basearch'  >> /etc/yum.repos.d/CentOS-Base.repo \
    && echo 'gpgcheck=1'  >> /etc/yum.repos.d/CentOS-Base.repo \
    && echo 'gpgkey=https://packages.erlang-solutions.com/rpm/erlang_solutions.asc'  >> /etc/yum.repos.d/CentOS-Base.repo \
    && echo 'enabled=1'  >> /etc/yum.repos.d/CentOS-Base.repo

RUN yum update -y && yum install -y erlang