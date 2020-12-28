FROM nginx:latest

RUN apt-get update && \
    apt-get install -y tzdata && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

RUN apt-get clean && \
  rm -rf /var/lib/apt/lists/*

COPY conf.d /etc/nginx/conf.d
