FROM nginx:alpine

RUN apk add --no-cache gettext

# Copiar plantilla de NGINX
COPY default.conf.template /etc/nginx/conf.d/default.conf.template

# Copiar archivos estáticos
COPY index.html /usr/share/nginx/html/
COPY app.js /usr/share/nginx/html/

EXPOSE 80

CMD ["/bin/sh", "-c", "envsubst '${BACKEND_HOST} ${BACKEND_PORT}' < /etc/nginx/conf.d/default.conf.template > /etc/nginx/conf.d/default.conf && nginx -g 'daemon off;'"]
