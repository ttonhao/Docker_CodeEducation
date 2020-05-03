FROM nginx:1.15-alpine
RUN apk add --no-cache openssl
ENV DOCKERIZE_VERSION v0.6.1
RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-alpine-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-alpine-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-alpine-linux-amd64-$DOCKERIZE_VERSION.tar.gz

WORKDIR /etc/nginx/conf.d/
RUN rm /etc/nginx/conf.d/*.conf
COPY ./nginx.conf .

CMD ["dockerize", "-template", "nginx.conf:nginx.conf", "nginx", "-g", "daemon off;"]