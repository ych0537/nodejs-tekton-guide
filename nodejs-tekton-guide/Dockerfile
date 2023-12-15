FROM registry.access.redhat.com/ubi8/nodejs-14@sha256:b241d5bdc8015baaeed0bbf66d2f934e72fa0b52263d62ce6b259ef343a0e6a7

USER root

WORKDIR /usr/src/app

COPY nodejs/package*.json ./

RUN npm install

# Bundle app source
COPY nodejs/. .

RUN chown -R 1001:0 /usr/src/app
USER 1001

EXPOSE 8080
CMD [ "node", "./bin/www" ]
