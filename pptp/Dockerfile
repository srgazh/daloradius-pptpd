FROM ubuntu:20.04
LABEL maintainer="srgazh@gmail.com"


ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -y pptpd iptables
RUN touch /var/log/pptpd.log
RUN apt-get install -y gcc wget build-essential 
RUN wget https://github.com/FreeRADIUS/freeradius-client/archive/master.tar.gz \
&& tar zxvf master.tar.gz \
&& cd freeradius-client-master\ 
&& ./configure --prefix=/ \
&& make \
&& make install
RUN rm master.tar.gz && rm -rf freeradius-client-master

COPY dictionary /etc/radiusclient/dictionary
COPY dictionary.microsoft /etc/radiusclient/dictionary.microsoft
COPY dictionary.pppd /etc/radiusclient/dictionary.pppd
COPY entrypoint.sh /entrypoint.sh
RUN chmod 0700 /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]
CMD ["pptpd", "--fg"]
