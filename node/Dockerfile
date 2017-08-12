FROM ubuntu

RUN apt-get update && \
    apt-get -y install curl

RUN curl -sL https://deb.nodesource.com/setup_6.x | bash

RUN apt-get install -y nodejs

RUN apt-get install -y build-essential

RUN mkdir /src

WORKDIR /src

ADD api/package.json /src/package.json

ADD /api /src

RUN npm install

RUN npm install nodemon -g

ADD api/nodemon.json /src/nodemon.json

RUN apt-get install nano -y

EXPOSE 3000

CMD npm start
