FROM node:8.16-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . /app

CMD sh ./entry-point.sh
