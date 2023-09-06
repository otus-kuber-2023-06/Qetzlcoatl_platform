FROM ubuntu:22.04
RUN mkdir /app/
RUN apt update && apt -y install nginx && rm -rf /var/lib/apt/lists/*
RUN usermod -u 1001 www-data && groupmod -g 1001 www-data
ADD nginx.conf /etc/nginx/nginx.conf
EXPOSE 8000
CMD ["nginx", "-g", "daemon off;"]