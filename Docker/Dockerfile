FROM alpine
MAINTAINER Badger Bill "Badger@gmail.com"
# Install Nginx:
RUN apk update  && apk add nginx && mkdir -p /usr/share/nginx/html
# Optionally Install some utilities:
RUN apk --no-cache add curl wget netcat-openbsd
## Copy a new configuration file setting listen port to 8083
COPY CONF/nginx.conf /etc/nginx/nginx.conf
COPY CONF/index.html /usr/share/nginx/html/
EXPOSE 80/tcp
## Get nginx to log to stdout and stderr
RUN ln -sf /dev/stdout /var/log/nginx/access.log && ln -sf /dev/stderr /var/log/nginx/error.log 
CMD ["nginx", "-g", "daemon off;"]
