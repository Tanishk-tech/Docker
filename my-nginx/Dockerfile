FROM ubuntu:24.04

RUN apt update  \
    && apt install nginx -y \
    && apt install vim -y \ 
    && apt install procps -y \
    && apt install net-tools -y 
    && apt install iproute2

WORKDIR /etc/nginx

ENV STAGE=4

COPY aehsc.conf conf.d/  

RUN rm -rf sites-enabled/* \
    && echo "<P> my name is tanishk hey we run docker container <p/>" > /usr/share/nginx/html/index.html 

EXPOSE 80 

ENTRYPOINT ["nginx"]

CMD ["-g" , "daemon off;"]



