FROM ubuntu:14.04
LABEL org.label-schema.name = "bsn-sn-1404"

# update packages and install ca-certificates
RUN apt-get update && apt-get -y upgrade && apt-get -y --no-install-recommends install \
    ca-certificates \
    curl \
    gnupg \
    wget

# Replace shell with bash so we can source files
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# make sure apt is up to date
RUN dpkg --add-architecture i386
RUN apt-get install -y software-properties-common
RUN add-apt-repository  ppa:george-edison55/cmake-3.x
RUN apt-get update --fix-missing
RUN apt-get install -y zip
RUN apt-get install -y cmake
RUN apt-get install -y ninja-build
RUN apt-get install -y doxygen
RUN apt-get install -y build-essential libssl-dev
#install lic for i386 architecture to build the intel edison node application
RUN apt-get install -y libc6:i386 libstdc++6:i386

#setup workdir etc
WORKDIR /home/user
