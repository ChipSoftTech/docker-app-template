# Set the base image to Ubuntu
FROM node:carbon

# Vendor & Version
LABEL       vendor="Chippewa Softare Technology"
LABEL       version="1.0.0-beta"

# Create app directory
VOLUME ./vdata/nodejs
WORKDIR ./vdata/nodejs

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
# Provides cached layer for node_modules
ADD package*.json /tmp/package.json
RUN cd /tmp && npm install
# If you are building your code for production
# RUN cd /tmp && npm install --only=production

#Copy over node modules to source code
RUN cp -a /tmp/node_modules ./vdata/nodejs

# Bundle app source
#COPY . .

# Expose port
EXPOSE  8080

# Run app using nodemon
#CMD ["nodemon", "start"]
# 
CMD [ "npm", "start" ]







