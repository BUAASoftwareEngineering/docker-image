FROM    ubuntu:18.04

# update apt
COPY    sources.list /etc/apt/sources.list
RUN     apt-get update --allow-unauthenticated

# build node enviroment
# RUN     apt-get install nodejs --allow-unauthenticated
# RUN     apt-get install npm --allow-unauthenticated

# install enviroment for terminal
RUN     apt-get install -y --assume-yes --allow-unauthenticated nodejs
RUN     apt-get install -y --assume-yes --allow-unauthenticated aptitude
RUN     apt-get install -y --assume-yes --allow-unauthenticated npm
RUN     apt-get install -y --assume-yes --allow-unauthenticated docker.io 

RUN     npm install pm2 -g

COPY    container-server /home/container-server
COPY    terminal         /home/terminal
COPY    start.sh 	 /home/start.sh
COPY    certs    	 /home/certs

WORKDIR /home/terminal
RUN     npm install

EXPOSE  3000 4000 5000

CMD     ["sh", "/home/start.sh"]
