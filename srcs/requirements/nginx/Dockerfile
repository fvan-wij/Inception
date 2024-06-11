FROM debian:bullseye

RUN apt -y update && apt install -y nginx && apt install openssl -y && \
    adduser --system --no-create-home --shell /bin/false --group --disabled-login nginx

RUN mkdir -p /etc/nginx/ssl

# Generate SSL certifcate and key
	#Distinguished Name (DN) codes
	#C=Country code
	#ST=State or province
	#L=Locality or city
	#O=Organization
	#OU=Organizational Unit
	#CN=Common Name
RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/nginx/ssl/nginx.key -out /etc/nginx/ssl/nginx.crt -subj "/C=NL/L=AMS/O=Codam/OU=student/CN=fvan-wij.codam.nl"

# RUN echo "<h1>hello world!</h1>" > /var/www/html/index.html

RUN ls -Rl /etc/nginx/ssl

COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 443

CMD	["nginx", "-g", "daemon off;"]
