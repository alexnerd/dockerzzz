FROM --platform=linux/arm64/v8 centos:latest
LABEL maintainer="Aleksey Popov, alexnerd.com" description="Base image with GraalVM 22.1 for all dockerzzz images"
RUN cd /etc/yum.repos.d/ \
  && sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-* \
  && sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-* \
  && yum update -y \
  && yum -y install unzip \
  && curl -O 'https://github.com/graalvm/graalvm-ce-builds/releases/download/vm-22.2.0/graalvm-ce-java17-linux-aarch64-22.2.0.tar.gz' -L \
  && mkdir -p /usr/lib/graalvm/ \
  && tar -xvf graalvm-ce-java17-linux-aarch64-22.2.0.tar.gz -C /usr/lib/graalvm/ \
  && rm graalvm-ce-java17-linux-aarch64-22.2.0.tar.gz \
  && yum -y install glibc-locale-source \
  && localedef -i en_US -f UTF-8 en_US.UTF-8 \
  && yum clean all 
ENV JAVA_TOOLS_OPTIONS=--enable-preview
ENV LC_ALL=en_US.UTF-8
ENV JAVA_HOME /usr/lib/graalvm/graalvm-ce-java17-22.2.0
ENV PATH /usr/lib/graalvm/graalvm-ce-java17-22.2.0/bin:$PATH
RUN gu install js