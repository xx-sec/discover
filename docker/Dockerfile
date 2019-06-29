FROM kalilinux/kali-linux-docker

RUN sed -i 's/deb/#deb/g' /etc/apt/sources.list
RUN echo "deb http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib" >> /etc/apt/sources.list
RUN echo "deb-src http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib" >> /etc/apt/sources.list


RUN apt-get install build-essential -y
RUN apt-get -y install curl wget gcc make git

WORKDIR /opt/
RUN git clone https://github.com/xx-sec/discover  /opt/discover
RUN cd /opt/discover && /bin/bash update.sh

USER root

CMD ['/bin/sh', '/opt/discover/discover.sh']

