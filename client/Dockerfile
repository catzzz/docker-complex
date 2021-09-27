FROM node:alpine as builder
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY .  .

RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./ngnix/default.conf /etc/nginx/confi.d/default.conf
COPY --from=builder /app/build /user/share/nginx/html