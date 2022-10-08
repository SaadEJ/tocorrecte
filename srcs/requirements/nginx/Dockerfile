
FROM	alpine:3.14


RUN		apk update


RUN		apk add --no-cache --quiet --update nginx
RUN		apk add --no-cache --quiet --update openssl

RUN		mkdir -p /etc/nginx/ssl


RUN 	openssl req -x509 -nodes \
	-out /etc/nginx/ssl/sejjed.42.fr.crt \	
	-keyout /etc/nginx/ssl/sejjed.42.fr.key \
	-subj "/C=FR/ST=IDF/L=Paris/O=42/OU=42/CN=sejjed.42.fr/UID=sejjed"


RUN 	mkdir -p /var/run/nginx


COPY	conf/nginx.conf /etc/nginx/http.d/default.conf


EXPOSE	443


CMD	[ "nginx", "-g", "daemon off;" ]
