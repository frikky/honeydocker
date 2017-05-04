FROM python:2.7-slim

WORKDIR /app

# Needs autogeneration
ADD honeyd.conf /app
ADD Honeyd/ /app

RUN apt-get update 
RUN apt-get install -y git libevent-dev libdumbnet-dev libpcap-dev libpcre3-dev libedit-dev bison flex libtool automake git zlib1g-dev make
RUN mv configure.in configure.ac
RUN ./autogen.sh
RUN ./configure
RUN make 
RUN make install 
RUN mkdir /app/logs
RUN touch "/app/logs/test.log"
RUN ls -alh /app
RUN ip a

# Ports
EXPOSE 445

CMD ["honeyd", "-d", "-i", "eth0"]
#"-d", "-f", "honeyd.conf", "-l", "/app/logs/test.log"]
