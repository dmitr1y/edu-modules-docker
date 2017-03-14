FROM ubuntu

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -y php7.0 apache2

RUN mkdir -p /usr/boolean-classes
#RUN git clone https://github.com/dmitr1y/discrete-eltech.git /usr/discrete-eltech

#RUN rm /usr/discrete-eltech/access.js
#ADD access.js /usr/discrete-eltech/

WORKDIR /usr/boolean-classes

CMD ["service ","apache2", "start"]

ENTRYPOINT cd /usr/boolean-classes && service apache2 restart
