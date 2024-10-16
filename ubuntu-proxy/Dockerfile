FROM ubuntu:22.04
RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y iproute2 inetutils-ping curl wget host mtr-tiny tcpdump net-tools iptables ncat traceroute nano python3 python3-pip vim git
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y sudo openssh-server
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y tmux unzip
RUN rm -rf /var/lib/apt/lists/*

RUN useradd -ms /bin/bash test && echo "test:test" | chpasswd
RUN mkdir /var/run/sshd
RUN sed -i 's/#PasswordAuthentication/PasswordAuthentication/g' /etc/ssh/sshd_config
RUN chmod -x /etc/update-motd.d/*
RUN echo "test ALL=(ALL:ALL) ALL" | tee -a /etc/sudoers

CMD ["/usr/sbin/sshd", "-D", "-e"]
