FROM node:8
MAINTAINER Jack Hu <hello@jackhu.top>

# Pre-install npm packages
RUN npm install -g node-gyp && \
    npm install -g pm2 && \
    npm cache clean --force && \
    rm -rf /tmp/* /var/tmp/*

RUN mkdir -p /var/www

ONBUILD WORKDIR /var/www
ONBUILD COPY . /var/www
ONBUILD RUN npm install --production
ONBUILD CMD ["npm", "start"]
