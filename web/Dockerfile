FROM grpc-chat-demo/proto:latest AS proto
FROM node:10

WORKDIR /grpc-web-chat/web

COPY --from=proto /grpc-web-chat/proto/ ../proto/

COPY package.json yarn.lock ./
RUN yarn --pure-lock

COPY ./ ./

RUN yarn build

FROM nginx:1.14-perl

COPY nginx.conf /etc/nginx/
COPY --from=1 /grpc-web-chat/web/dist/ /var/www/
