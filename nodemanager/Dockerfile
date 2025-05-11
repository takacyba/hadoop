FROM bde2020/hadoop-base:2.0.0-hadoop3.2.1-java8


HEALTHCHECK CMD curl -f http://localhost:8042/ || exit 1

ADD run.sh /run.sh
RUN chmod a+x /run.sh

EXPOSE 8042

CMD ["/run.sh"]

RUN echo "deb http://archive.debian.org/debian stretch main" > /etc/apt/sources.list
RUN apt-get update -y; apt-get install -y python3 python3-pip; apt-get clean; rm -rf /var/lib/apt/lists/*
RUN ln -s /usr/bin/python3 /usr/bin/python && ln -s /usr/bin/pip3 /usr/bin/pip
