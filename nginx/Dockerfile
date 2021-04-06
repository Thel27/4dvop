FROM ubuntu:20.04
ENV DEBIAN_FRONTEND noninteractive
RUN apt update && apt install -y nginx git && \
	rm /var/www/html/* && \
	rm -rf /var/lib/apt/lists/* && \
	git clone https://github.com/diranetafen/static-website-example.git /var/www/html && \
	sed -i 's/80 default_server/8090 default_server/g' /etc/nginx/sites-enabled/default

EXPOSE 8080

ENTRYPOINT ["/usr/sbin/nginx","-g","daemon off;"]
