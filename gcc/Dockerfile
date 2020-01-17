FROM ubuntu:18.04

RUN apt-get update >/dev/null && \
    apt-get install -y \
    apt-utils \
    build-essential \
    gnupg2 \
    curl \
    xz-utils \
    wget \
    >/dev/null && \
    echo 'deb http://ppa.launchpad.net/jonathonf/gcc-9.2/ubuntu bionic main' > /etc/apt/sources.list.d/gcc.list && \
    wget -O - 'https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x4ab0f789cba31744cc7da76a8cf63ad3f06fc659' | apt-key add - && \
    apt-get update >/dev/null && \
    apt-get install -y \
    gcc-9 g++-9 \
    >/dev/null && \
    update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-9 100 && \
    update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-9 100 && \
    update-alternatives --install /usr/bin/cc cc /usr/bin/gcc 100 && \
    update-alternatives --install /usr/bin/c++ c++ /usr/bin/g++ 100 && \
    rm -rf /var/lib/apt/lists/*
