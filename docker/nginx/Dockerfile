FROM nginx:1.21.4-alpine

RUN apt update && apt install -y \
    wget \
    vim  \
    net-tools  \
    coreutils

RUN echo "set mouse-=a" >> ~/.vimrc

ADD ./config/default.conf /etc/nginx/conf.d/default.conf

WORKDIR /symfony