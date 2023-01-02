FROM --platform=linux/amd64 centos:latest
LABEL maintainer="Aleksey Popov, alexnerd.com" description="Base image with JDK 11 for all dockerzzz images"
RUN cd /etc/yum.repos.d/ \
  && sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-* \
  && sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-* \
  && yum update -y \
  && yum -y install unzip \
  && yum -y install java-11-openjdk-devel \
  && yum -y install glibc-locale-source \
  && localedef -i en_US -f UTF-8 en_US.UTF-8 \
  && yum clean all

ENV LC_ALL=en_US.UTF-8
ENV JAVA_HOME /usr/lib/jvm/java-11
ENV PATH "$PATH":.w