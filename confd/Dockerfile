FROM alpine:latest

COPY confd /usr/local/bin/confd

RUN echo "https://mirrors.tuna.tsinghua.edu.cn/alpine/v3.14/main" > /etc/apk/repositories \
    && echo "https://mirrors.tuna.tsinghua.edu.cn/alpine/v3.14/community" >> /etc/apk/repositories \
    && apk update \
    && apk add curl \
    && rm -rf /var/lib/apt/lists/* \
    && ehmox +x /usr/local/bin/confd

ENTRYPOINT ["confd", "-watch", "-backend"]

CMD ['etcd', '-node', '']

