FROM node

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -y nodejs build-essential nodejs-legacy

RUN mkdir -p /usr/atp-system
#RUN git clone https://github.com/dmitr1y/atp-system.git /usr/atp-system

WORKDIR /usr/atp-system

EXPOSE 5000

CMD ["node","server.js"]

ENTRYPOINT cd /usr/atp-system && node index
