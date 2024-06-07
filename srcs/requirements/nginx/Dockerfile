FROM debian:bullseye

RUN apt -y update && apt install -y nginx && apt install openssl -y

# Generate SSL certifcate and key
RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/nginx/ssl/fvan-wij.key -out /etc/nginx/ssl/fvan-wij.crt -subj "/C=MO/L=KH/O=1337/OU=student/CN=fvan-wij.42.ma"

COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

CMD	["nginx", "-g", "daemon off;"]
