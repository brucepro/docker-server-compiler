FROM ubuntu:18.04

RUN apt-get update >/dev/null && \
    apt-get install -y \
    apt-utils \
    build-essential \
    curl \
    xz-utils \
    wget \
    >/dev/null && \
    echo 'deb http://apt.llvm.org/bionic/ llvm-toolchain-bionic main' > /etc/apt/sources.list.d/clang.list && \
    wget -O - https://apt.llvm.org/llvm-snapshot.gpg.key | apt-key add - && \
    apt-get update >/dev/null && \
    apt-get install -y \
    clang-10 clang-tools-10 libc++-10-dev libc++abi-10-dev \
    >/dev/null && \
    update-alternatives --install /usr/bin/clang clang /usr/bin/clang-10 100 && \
    update-alternatives --install /usr/bin/clang++ clang++ /usr/bin/clang++-10 100 && \
    update-alternatives --install /usr/bin/cc cc /usr/bin/clang 100 && \
    update-alternatives --install /usr/bin/c++ c++ /usr/bin/clang++ 100 && \
    rm -rf /var/lib/apt/lists/*
