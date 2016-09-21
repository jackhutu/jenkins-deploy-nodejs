FROM node:5.12
MAINTAINER Jack Hu <hello@jackhu.top>

# Pre-install npm packages
RUN npm install -g node-gyp && \
    npm install -g cnpm && \
    npm install -g pm2 && \
    npm cache clean && \
    rm -rf /tmp/* /var/tmp/*

RUN mkdir /var/www

ONBUILD ADD . /var/www
ONBUILD WORKDIR /var/www
ONBUILD cnpm install --production

EXPOSE	3000

CMD ["npm", "run", "pm2-start"]
