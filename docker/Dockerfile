FROM node:9-alpine

ADD . /jsketcher/

WORKDIR /jsketcher

RUN echo "Installing dependencies..." \
 && npm install \
 && echo "Building..." \
 && ./node_modules/.bin/webpack --config webpack.config.js --progress \
 && mv dist/static web/ \
 && echo "Installating static server..." \
 && npm install node-static
 
 EXPOSE 3000
 
WORKDIR /jsketcher/web/
CMD ["../node_modules/.bin/static","-a","0.0.0.0","-p","3000"]
