FROM ubuntu:22.04
RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y iproute2 inetutils-ping curl wget host mtr-tiny tcpdump iptables ncat traceroute nano vim net-tools \
    && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["/bin/bash"]