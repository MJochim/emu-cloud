FROM node:8

RUN apt-get update && apt-get install -y \
	git \
    && rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/IPS-LMU/IPS-EMUprot-nodeWSserver.git /code
WORKDIR /code
RUN npm install

RUN git config --file /etc/gitconfig user.name 'EMU Cloud Websocket Protocol'
RUN git config --file /etc/gitconfig user.email 'nobody@example.com'

CMD node /code/IPS-EMUprot-nodeWSserver.js /etc/emu-cloud/websocket_server_config.json | node_modules/bunyan/bin/bunyan
