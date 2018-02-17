FROM node

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -y apt-utils nodejs build-essential nodejs-legacy

RUN mkdir -p /usr/atp-system
#RUN git clone https://github.com/dmitr1y/atp-system.git /usr/atp-system

WORKDIR /usr/atp-system

CMD ["node","index.js"]

ENTRYPOINT cd /usr/atp-system && node index
