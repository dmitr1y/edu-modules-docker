FROM ubuntu

MAINTAINER Dmitrii Konstantinov

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -y apt-utils nginx curl

RUN rm -f /etc/service/nginx/down
RUN rm /etc/nginx/sites-enabled/default

RUN mkdir /www
RUN mkdir /www/modules

ADD default /etc/nginx/sites-enabled/
ADD main /etc/nginx/sites-enabled/
#ADD shell /etc/nginx/sites-enabled/
#ADD evklid-trainer /etc/nginx/sites-enabled/
#ADD atp-system /etc/nginx/sites-enabled/
#ADD boolean-solver /etc/nginx/sites-available/

RUN echo "daemon off;" >> /etc/nginx/nginx.conf

CMD ["nginx", "-g", "daemon off;"]
ENTRYPOINT service nginx start && bash
