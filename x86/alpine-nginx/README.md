# alpine-nginx

## 迷你nginx

```
FROM alpine:latest
MAINTAINER wuyue92tree@163.com

RUN apk update && apk add nginx tzdata \
    && cp -r -f /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && mkdir /run/nginx/ \
    && echo "daemon off;" >> /etc/nginx/nginx.conf

EXPOSE 80
EXPOSE 443

CMD ["nginx"]
```

- 修改时区为上海
- 以daemon off模式启动nginx
- 配置文件目录“/etc/nginx/conf.d”, 默认为“/etc/nginx/conf.d/default.conf”
