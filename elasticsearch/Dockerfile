FROM mar2max/docker-vt-ubuntu
MAINTAINER Amamou Marwan <amamou.marwan@gmail.com>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update
RUN apt-get install openjdk-7-jre-headless -y

RUN cd /tmp && \
  wget https://download.elasticsearch.org/elasticsearch/elasticsearch/elasticsearch-1.4.4.tar.gz && \
  tar xvzf elasticsearch-1.4.4.tar.gz && \
  rm -f elasticsearch-1.4.4.tar.gz && \
  mv /tmp/elasticsearch-1.4.4 /elasticsearch

VOLUME ["/data"]
ADD elasticsearch.yml /elasticsearch/config/elasticsearch.yml

RUN /elasticsearch/bin/plugin --url https://github.com/SibaTokyo/elasticsearch-image/releases/download/1.4.0/elasticsearch-image-1.4.0.zip -install image

WORKDIR /data

CMD ["/elasticsearch/bin/elasticsearch"]

EXPOSE 9200
EXPOSE 9300

RUN apt-get autoremove && \
    apt-get autoclean && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*