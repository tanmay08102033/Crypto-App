FROM node:lts

WORKDIR /app

ENV PATH /app/node_modules/.bin:$PATH

COPY ./package.json /app/
COPY ./package-lock.json /app/

RUN npm install

COPY . /app

RUN npm run build

RUN npm install -g serve

EXPOSE 80

# Serve
ENTRYPOINT [ "serve" ]
CMD [ "-s", "build", "-p", "80"]