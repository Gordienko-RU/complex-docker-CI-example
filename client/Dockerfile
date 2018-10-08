# tag block to refering
FROM node:alpine as builder
WORKDIR /home/server
COPY package.json .
RUN npm install
COPY . .
RUN ["npm", "run", "build"]

# on second step use another core image
FROM nginx

COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
# copy files builded on previous step
COPY --from=builder /home/server/build /usr/share/nginx/html