FROM mar2max/docker-vt-elasticsearch
MAINTAINER Amamou Marwan <amamou.marwan@gmail.com>

VOLUME ["/data"]
WORKDIR /data

RUN /elasticsearch/bin/plugin -i elasticsearch/marvel/latest

CMD ["/elasticsearch/bin/elasticsearch"]

EXPOSE 9200
EXPOSE 9300