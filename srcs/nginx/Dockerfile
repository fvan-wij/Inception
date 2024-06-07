FROM debian:bullseye

# LABEL maintainer="fvan-wij@student.codam.nl"

RUN apt-get update && \
	apt-get install -y nginx && \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/*

# Generate SSL certifcate and key
RUN 

COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

CMD	["nginx", "-g", "daemon off;"]
