# Set the base image to Ubuntu
FROM        ubuntu

# Vendor & Version
LABEL       vendor="Chippewa Softare Technology"
LABEL       version="1.0.0-beta"

# Update the repository and install Redis Server
RUN         apt-get update && apt-get install -y redis-server

# Expose Redis port 6379
EXPOSE      6379

# Define mountable directories.
RUN mkdir ./vdata/redis
VOLUME ./vdata/redis
WORKDIR ./vdata/redis

# Run Redis Server
ENTRYPOINT  ["/usr/bin/redis-server"]
