FROM    node:13
RUN     npm install pm2 -g

# update apt
COPY    sources.list /etc/apt/sources.list
RUN     apt-get update --allow-unauthenticated

# install enviroment for terminal
RUN     apt-get install -y --allow-unauthenticated make python build-essential
RUN     apt-get install docker.io

COPY    container-server /home/container-server
COPY    terminal         /home/terminal
COPY    start.sh 	 /home/start.sh
COPY    certs    	 /home/certs

WORKDIR /home/terminal
RUN     npm install

EXPOSE  3000 4000 5000

CMD     ["sh", "/home/start.sh"]
