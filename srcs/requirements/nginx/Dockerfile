FROM debian:bullseye

RUN apt -y update && apt install -y nginx && apt install openssl -y && \
    adduser --system --no-create-home --shell /bin/false --group --disabled-login nginx

# Generate SSL certifcate and key
	#Distinguished Name (DN) codes
	#C=Country code
	#ST=State or province
	#L=Locality or city
	#O=Organization
	#OU=Organizational Unit
	#CN=Common Name
RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/nginx/fvan-wij.key -out /etc/nginx/fvan-wij.crt -subj "/C=NL/L=AMS/O=Codam/OU=student/CN=localhost"

COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

CMD	["nginx", "-g", "daemon off;"]
