FROM node:carbon
RUN apt-get update
RUN mkdir /app && \
    git clone https://github.com/wtfdiov/ristorant-app /app && \
    cd app && \
    npm install && \
    npm run build

FROM nginx:1.13-alpine
COPY --from=0 /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
