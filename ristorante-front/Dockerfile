# FROM node

# RUN apt-get update
# RUN mkdir /app && \
#     git clone https://github.com/dougdelabrida/bolao-webwallet /app && \
#     cd /app && \
#     npm install --production && \
#     chmod +x start.sh

# WORKDIR /app

# CMD ["/app/start.sh"]

FROM node:carbon

RUN apt-get update
RUN mkdir /app && \
    git clone https://vitor.santos:Systemofadown_15@gitlab.sysmap.com.br/sistemas/bolao-webwallet.git /app && \
    cd app && \
    npm install && \
    npm run build

FROM nginx:1.13-alpine
COPY --from=0 /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
