FROM    node:13
RUN     npm install pm2 -g

RUN	echo "deb http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse" > /etc/apt/sources.list
RUN	echo "deb http://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse" >> /etc/apt/sources.list
RUN	echo "deb http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse" >> /etc/apt/sources.list
RUN	echo "deb http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse" >> /etc/apt/sources.list
RUN     apt-get update
RUN     apt-get install -y --allow-unauthenticated make python build-essential

COPY    container-server /home/container-server
COPY    terminal /home/terminal
COPY    start.sh /home/start.sh

EXPOSE  3000
EXPOSE  4001

CMD     ["sh", "/home/start.sh"]
