FROM debian:bullseye

RUN apt -y update
RUN apt install -y nginx 
RUN apt install openssl -y
RUN useradd -r nginx

# Creates a directory to store ssl cert and key 
RUN mkdir -p /etc/nginx/ssl	
RUN mkdir -p /var/www/wordpress
RUN chown -R www-data:www-data /var/www/wordpress

# Generate SSL certifcate and key
	#Distinguished Name (DN) codes
	#C=Country code
	#ST=State or province
	#L=Locality or city
	#O=Organization
	#OU=Organizational Unit
	#CN=Common Name
RUN openssl req \
	-x509 \
	-nodes \
	-days 365 \
	-newkey rsa:2048 \
	-keyout /etc/nginx/ssl/nginx.key \
	-out /etc/nginx/ssl/nginx.crt \
	-subj "/C=NL/ST=Noord Holland/L=Amsterdam/O=Codam/OU=Flip/CN=fvan-wij"

COPY /conf/nginx.conf /etc/nginx/nginx.conf

EXPOSE 443

# CMD	["nginx", "-g", "daemon off;"]
ENTRYPOINT	["nginx", "-g", "daemon off;"]
