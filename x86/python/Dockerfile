FROM python:2.7.14
MAINTAINER wuyue92tree@163.com

WORKDIR /data/src

COPY pip.conf /root/.pip/pip.conf

RUN pip install supervisor \
    && pip install -r requirements.txt \
    && mkdir -p /etc/supervisor/conf.d \
    && echo_supervisord_conf > /etc/supervisor/supervisord.conf \
    &&