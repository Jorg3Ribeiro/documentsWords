FROM node:16.13.1

WORKDIR /home/app

COPY package*.json ./

RUN apt-get update
RUN apt-get upgrade -y 
RUN apt-get install nano -y
RUN apt install git curl build-essential libssl-dev libffi-dev python-dev libudev-dev -y
RUN npm install
RUN npm install -g pm2
RUN npm install -g http-server

ENV TZ=America/Bahia
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get install vim -y

COPY . /home/app

COPY --chown=root:root . .

USER root

EXPOSE 3001
CMD [ "npm", "start"]