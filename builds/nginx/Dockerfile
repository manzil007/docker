FROM ubuntu
MAINTAINER vmsnivas <vmsnivas@gmail.com>

# Install Nginx

# Add application repository URL to the default sources
# RUN echo "deb http://archive.ubuntu.com/ubuntu/ raring main universe" >> /etc/apt/sources.list

# Add User and Group
CMD ["addgroup -S nginx"]
CMD ["adduser -D -S -h /var/cache/nginx -s /sbin/nologin -G nginx nginx"]

# Update the repository
RUN apt-get update && apt-get install -y nano wget dialog net-tools nginx

# Remove the default Nginx configuration file
RUN rm -v /etc/nginx/nginx.conf

# Copy Config files
COPY nginx.conf /etc/nginx/nginx.conf
COPY nginx.vh.default.conf /etc/nginx/conf.d/default.conf


# Expose ports
EXPOSE 80 443

# Set the default command to execute
# when creating a new container
CMD ["nginx -t"]
CMD ["nginx","-g","daemon off"]

HEALTHCHECK CMD ["curl http://localhost/ || exit 1"]
