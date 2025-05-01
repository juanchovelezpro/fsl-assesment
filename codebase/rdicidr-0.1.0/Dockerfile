FROM node:15 AS builder

WORKDIR /app

COPY package*.json /app

RUN npm install

COPY . .

RUN npm run build

FROM nginx:alpine AS production

#WORKDIR 

COPY --from=builder /app/build /usr/share/nginx/html

#RUN 

ENTRYPOINT ["nginx", "-g", "daemon off;"]