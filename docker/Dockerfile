FROM rabbitmq:3.8.2-management-alpine

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories
RUN apk add tzdata && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo "Asia/Shanghai" > /etc/timezone \
    && apk del tzdata

EXPOSE 15671
EXPOSE 15672
EXPOSE 5671
EXPOSE 5672
EXPOSE 1883
EXPOSE 8883

RUN echo "2020031802" >> /dev/null
RUN date
RUN rabbitmq-plugins enable rabbitmq_management
RUN rabbitmq-plugins enable rabbitmq_auth_mechanism_ssl
RUN rabbitmq-plugins enable rabbitmq_mqtt

CMD ["rabbitmq-server"]