FROM nginx:1.17

RUN apt update && apt install -y \
    wget \
    vim  \
    net-tools  \
    coreutils

RUN echo "set mouse-=a" >> ~/.vimrc

ADD ./config/default.conf /etc/nginx/conf.d/default.conf

WORKDIR /symfony