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