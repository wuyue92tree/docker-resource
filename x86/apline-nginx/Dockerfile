FROM apline:latest
MAINTAINER wuyue92tree@163.com

RUN apk update && apk add curl bash tree tzdata \
    && cp -r -f /usr/share/zoneinfo/Asia/Hong_kong /etc/localtime \
    && mkdir /run/nginx/ \
    && echo "daemon off" >> /etc/nginx/nginx.conf

EXPOSE 80
EXPOSE 443

CMD ["nginx"]