# Copyright (c) 2015 Martin Stumpf
#
# Distributed under the Boost Software License, Version 1.0. (See accompanying
# file LICENSE_1_0.txt or copy at http://www.boost.org/LICENSE_1_0.txt)

FROM ubuntu:bionic

# Update and install libraries
RUN apt-get update && apt-get install -y curl gnupg && \
    echo "deb http://apt.llvm.org/bionic/ llvm-toolchain-bionic-7 main" >> /etc/apt/sources.list && \
    echo "deb-src http://apt.llvm.org/bionic/ llvm-toolchain-bionic-7 main" >> /etc/apt/sources.list && \
    curl https://apt.llvm.org/llvm-snapshot.gpg.key | apt-key add -

RUN export DEBIAN_FRONTEND=noninteractive &&        \
    apt-get update && apt-get install -y            \
                    clang-7                         \
                    clang-7-doc                     \
                    libclang-common-7-dev           \
                    libclang-7-dev                  \
                    libclang1-7                     \
                    libllvm7                        \
                    llvm-7                          \
                    llvm-7-dev                      \
                    llvm-7-runtime                  \
                    clang-format-7                  \
                    clang-tidy-7                    \
                    lld-7                           \
                    libhwloc-dev                    \
                    libjemalloc-dev                 \
                    cmake                           \
                    libboost-atomic-dev             \
                    libboost-chrono-dev             \
                    libboost-date-time-dev          \
                    libboost-filesystem-dev         \
                    libboost-program-options-dev    \
                    libboost-regex-dev              \
                    libboost-system-dev             \
                    libboost-thread-dev             \
                    doxygen                         \
                    python                          \
                    python-sphinx                   \
                    python-sphinx-rtd-theme         \
                    python-breathe                  \
                    libjson-perl                    \
                    ninja-build                     \
                    git                             \
                    xsltproc                        \
                    pkg-config &&                   \
    update-alternatives --install /usr/bin/clang++  \
        clang++ /usr/bin/clang++-7 100 &&           \
    update-alternatives --install /usr/bin/clang    \
        clang /usr/bin/clang-7 100 &&               \
    update-alternatives --install /usr/bin/clang-tidy \
        clang-tidy /usr/bin/clang-tidy-7 100 &&     \
    rm /usr/bin/ld && ln -s /usr/bin/ld.lld-7 /usr/bin/ld

ENV CC clang
ENV CXX clang++