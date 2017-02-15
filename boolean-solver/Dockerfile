FROM node:6.5.0

ENV DEBIAN_FRONTEND noninteractive
RUN export USER=root
RUN export HOME=/tmp

RUN apt-get update && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_6.x | bash
RUN apt-get install -y nodejs build-essential libavahi-compat-libdnssd-dev
COPY boolean-solver /usr/boolean-solver
WORKDIR /usr/boolean-solver
RUN rm -rf /usr/boolean-solver/node_modules/libxmls
RUN cd /usr/boolean-solver && npm install libxmljs

CMD ["node","www.js"]

ENTRYPOINT cd /usr/boolean-solver/bin && node www
