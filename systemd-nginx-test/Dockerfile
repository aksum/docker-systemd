FROM ubuntu:16.04
ENV container docker
RUN apt-get update && \
    apt-get install --no-install-recommends --no-install-suggests -y nginx && \
    apt-get clean
RUN systemctl enable nginx
STOPSIGNAL SIGRTMIN+3
EXPOSE 80
CMD [ "/sbin/init" ]

