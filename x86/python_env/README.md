# python_env

## python运行环境优化

```
FROM python:2.7.14
MAINTAINER wuyue92tree@163.com

WORKDIR /data/src

ADD pip.conf /root/.pip/pip.conf

ADD requirements.txt requirements.txt

RUN pip install supervisor==3.3.3 \
    && pip install -r requirements.txt \
    && mkdir -p /etc/supervisor/conf.d \
    && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

ADD supervisord.conf /etc/supervisor/supervisord.conf

EXPOSE 9001

CMD supervisord -n -c /etc/supervisor/supervisord.conf
```

- 修改pip下载源为国内源(豆瓣)
- 镜像build时，传入requirements.txt以安装依赖
- 采用supervisor作为守护进程启动项目，配置目录“/etc/supervisor/conf.d”
- 更改docker时区为上海
- 开启supervisor web端管理，默认无认证信息
