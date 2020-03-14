FROM rabbitmq:3.8.2-management-alpine

RUN apk add tzdata && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo "Asia/Shanghai" > /etc/timezone \
    && apk del tzdata

EXPOSE 15671
EXPOSE 15672
EXPOSE 5671
EXPOSE 5672

RUN echo "2020031301" >> /dev/null
RUN date
RUN rabbitmq-plugins enable rabbitmq_management
RUN rabbitmq-plugins enable rabbitmq_auth_mechanism_ssl

CMD ["rabbitmq-server"]