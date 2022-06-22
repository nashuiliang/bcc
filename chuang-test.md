# Test (chuang)

## Environment

ubuntu:22.04

```bash
$ docker pull ubuntu:22.04
```

build environment

```bash
# Before you begin
apt-get update
# According to https://packages.debian.org/source/sid/bpfcc,
# BCC build dependencies:
sudo apt-get install arping bison clang-format cmake dh-python \
  dpkg-dev pkg-kde-tools ethtool flex inetutils-ping iperf \
  libbpf-dev libclang-dev libclang-cpp-dev libedit-dev libelf-dev \
  libfl-dev libzip-dev linux-libc-dev llvm-dev libluajit-5.1-dev \
  luajit python3-netaddr python3-pyroute2 python3-distutils python3
```

build

```bash
$ docker run --rm -it --privileged -v /data/projects/bcc:/data/projects/bcc -v /lib/modules/:/lib/modules/ -v /usr/src/:/usr/src/ ubuntu:22.04-base bash
(oci)$ cd /data/projects/bcc
(oci)$ mkdir build
(oci)$ cd build
(oci)$ cmake ..
(oci)$ make && make install
```
