FROM ubuntu

MAINTAINER Dmitrii Konstantinov

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -y apt-utils nginx

RUN rm -f /etc/service/nginx/down
RUN rm /etc/nginx/sites-enabled/default

ADD default /etc/nginx/sites-available/
ADD main /etc/nginx/sites-available/
ADD evklid-trainer /etc/nginx/sites-available/
ADD atp-system /etc/nginx/sites-available/

RUN ln -s /etc/nginx/sites-available/default /etc/nginx/sites-enabled/default
RUN ln -s /etc/nginx/sites-available/main /etc/nginx/sites-enabled/main
RUN ln -s /etc/nginx/sites-available/evklid-trainer /etc/nginx/sites-enabled/evklid-trainer
RUN ln -s /etc/nginx/sites-available/evklid-trainer /etc/nginx/sites-enabled/atp-system

RUN echo "daemon off;" >> /etc/nginx/nginx.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
ENTRYPOINT service nginx start && bash
