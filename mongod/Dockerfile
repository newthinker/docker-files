#
# MongoDB Dockerfile
#
# https://github.com/newthinker/mongodb
#

# Base image
FROM dockerfile/ubuntu

# Maintainer
MAINTAINER Michael zuow11@gmail.com

# Install MongoDB
RUN \
  apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10 && \
  echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' > /etc/apt/sources.list.d/mongodb.list && \
  apt-get update && \
  apt-get install -y mongodb-org && \
  rm -rf /var/lib/apt/lists/*

# Define mountable directories
VOLUME ["/visualops/db"]

# Define working directory.
WORKDIR /visualops

# Define entrypoint
ENTRYPOINT ["/usr/bin/mongod", "-f", "/visualops/conf/mongod.conf"]

# Define default command.
CMD ["--help"]

# Expose ports.
#   - 8290: process
EXPOSE 8290