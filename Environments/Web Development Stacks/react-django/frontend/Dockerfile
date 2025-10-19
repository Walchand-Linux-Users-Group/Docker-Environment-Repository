FROM node:latest AS build
WORKDIR /app

COPY package.json /app/package.json
COPY package-lock.json /app/package-lock.json

RUN npm install

COPY . /app/

#dev deploy
#EXPOSE 3000
#CMD ["npm","start"]

#production deploy
RUN npm run build

FROM nginx:alpine AS prod

COPY --from=build /app/dist /usr/share/nginx/html
EXPOSE 80

CMD ["nginx","-g","daemon off;"]
