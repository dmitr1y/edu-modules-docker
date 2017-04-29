FROM node:6.5.0

ENV DEBIAN_FRONTEND noninteractive
RUN export USER=root
RUN export HOME=/tmp

RUN apt-get update && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_6.x | bash
RUN apt-get install -y nodejs build-essential libavahi-compat-libdnssd-dev
#COPY boolean-solver /usr/boolean-solver
RUN mkdir /usr/boolean-solver
WORKDIR /usr/boolean-solver

# Fix for "EXDEV: cross-device link not permitted", see https://github.com/npm/npm/issues/9863
RUN cd $(npm root -g)/npm && npm install fs-extra && sed -i -e s/graceful-fs/fs-extra/ -e s/fs\.rename/fs.move/ ./lib/utils/rename.js

RUN rm -rf /usr/boolean-solver/node_modules/libxmls
RUN cd /usr/boolean-solver && npm install libxmljs

CMD ["node","www.js"]

ENTRYPOINT cd /usr/boolean-solver/bin && node www
