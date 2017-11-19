FROM alpine:latest
MAINTAINER wuyue92tree@163.com

RUN apk update && apk add nginx tzdata \
    && cp -r -f /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && mkdir /run/nginx/ \
    && echo "daemon off;" >> /etc/nginx/nginx.conf

EXPOSE 80
EXPOSE 443

CMD ["nginx"]