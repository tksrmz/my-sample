FROM ubuntu:22.04

RUN apt-get update && apt-get install -y \
    apache2 \
    monit \
    && rm -rf /var/lib/apt/lists/*

RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf

COPY monitrc /etc/monit/monitrc
RUN chmod 600 /etc/monit/monitrc

EXPOSE 80 2812

# Monitを直接PID 1として起動
ENTRYPOINT ["/usr/bin/monit", "-I"]
