FROM node:6.5.0

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -y nodejs build-essential nodejs-legacy

RUN mkdir -p /usr/boolean-solver
#RUN git clone https://github.com/dmitr1y/atp-system.git /usr/atp-system

WORKDIR /usr/boolean-solver

CMD ["node","www.js"]

ENTRYPOINT cd /usr/boolean-solver/bin && node www
