FROM node

RUN apt-get update
RUN mkdir /app && \
    git clone https://github.com/matcabgomes/ristorante-menu.git /app && \
    cd /app && \
    npm install --production && \
    chmod +x start.sh

WORKDIR /app

CMD ["/app/start.sh"]