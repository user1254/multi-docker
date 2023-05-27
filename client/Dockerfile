FROM node:16-alpine as builder
WORKDIR '/app'
COPY .packge.json .
RUN npm intall
CMD ['npm', 'run', 'build']

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --FROM=builder /app/build /usr/share/nginx/html