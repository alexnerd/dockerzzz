FROM --platform=linux/arm64/v8 centos:latest
LABEL maintainer="Aleksey Popov, alexnerd.com" description="Base image with JDK 17 for all dockerzzz images"
RUN cd /etc/yum.repos.d/ \
  && sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-* \
  && sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-* \
  && yum update -y \
  && yum -y install unzip \
  && yum -y install java-17-openjdk \
  && yum clean all