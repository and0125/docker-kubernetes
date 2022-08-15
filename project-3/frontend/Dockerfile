# Phase 1: Node.js build-stage

FROM node:alpine as builder 

RUN mkdir /app
WORKDIR '/app'
COPY pacakge.json .
RUN npm install
COPY . . 
RUN npm run build 

# Phase 2: Nginx hosting

FROM nginx
COPY --from=builder /app/build /usr/share/nginx/html
