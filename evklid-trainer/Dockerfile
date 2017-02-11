FROM node

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -y nodejs build-essential nodejs-legacy

RUN mkdir -p /usr/discrete-eltech
#RUN git clone https://github.com/dmitr1y/discrete-eltech.git /usr/discrete-eltech

#RUN rm /usr/discrete-eltech/access.js
#ADD access.js /usr/discrete-eltech/

WORKDIR /usr/discrete-eltech

CMD ["node","index.js"]

ENTRYPOINT cd /usr/discrete-eltech && node index
