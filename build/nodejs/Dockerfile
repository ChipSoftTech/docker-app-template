# Set the base image to Ubuntu
FROM    ubuntu:trusty

# Vendor & Version
LABEL       vendor="Chippewa Softare Technology"
LABEL       version="1.0.0-beta"

# Install Node.js and other dependencies
RUN apt-get update && \
    apt-get -y install curl && \
    curl -sL https://deb.nodesource.com/setup | sudo bash - && \
    apt-get -y install python build-essential nodejs

# Install nodemon
RUN npm install -g nodemon

# Provides cached layer for node_modules
ADD package.json /tmp/package.json
RUN cd /tmp && npm install
RUN mkdir -p /src && cp -a /tmp/node_modules /src/

# Define working directory
RUN mkdir ./vdata/nodejs
VOLUME ./vdata/nodejs
WORKDIR ./vdata/nodejs
ADD . ./vdata/nodejs

# Expose port
EXPOSE  8080

# Run app using nodemon
CMD ["nodemon", "/src/index.js"]