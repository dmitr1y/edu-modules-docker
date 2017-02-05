FROM node

MAINTAINER Seraphim Urukov

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -y nodejs build-essential nodejs-legacy

RUN mkdir -p /usr/discrete-eltech
#COPY ./discrete-eltech-master/ /usr/api
RUN git clone https://github.com/mifarse/discrete-eltech.git /usr/discrete-eltech
RUN rm /usr/discrete-eltech/db.js
RUN rm /usr/discrete-eltech/index.js
ADD db.js /usr/discrete-eltech/
ADD index.js /usr/discrete-eltech/
WORKDIR /usr/discrete-eltech
#RUN npm install



EXPOSE 8888

CMD ["node","index.js"]

ENTRYPOINT cd /usr/discrete-eltech && node index