FROM debian
# changing to debian because of https://github.com/docker/hub-feedback/issues/461
MAINTAINER Daisuke Shinmachi "d.shinmachi.aist@gmail.com", Issaku Yamada "yamadaissaku@gmail.com"

#RUN yum install --nogpgcheck -y httpd 
#RUN yum install -y git
#RUN yum install -y wget

#RUN echo "Acquire::http { Proxy \"http://test.glytoucan.org:3142\"; };" > /etc/apt/apt.conf.d/02Proxy
RUN apt-get update && apt-get install -y git wget && rm -rf /var/lib/apt/lists/*

RUN mkdir /stanza

WORKDIR /stanza
RUN wget https://github.com/togostanza/ts/releases/download/v0.0.9/ts_0.0.9_linux_amd64.tar.gz
RUN tar zxf ts_0.0.9_linux_amd64.tar.gz 
RUN cp ts_0.0.9_linux_amd64/ts /bin

VOLUME /stanza/stanza_provider 
WORKDIR /stanza/stanza_provider 

EXPOSE 8080
# CMD ["/stanza/ts_0.0.9_linux_amd64/ts", "server"]
# CMD ["/usr/local/bin/ts", "server"]
# CMD ["/stanza/ts_0.0.9_linux_amd64/ts", "build"]
CMD ["ts", "server"]

