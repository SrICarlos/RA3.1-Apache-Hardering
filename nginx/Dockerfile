FROM nginx:stable

# Copiar configuración personalizada
COPY nginx.conf /etc/nginx/nginx.conf

# Crear certificados autofirmados
RUN mkdir -p /etc/nginx/ssl && \
    openssl req -x509 -nodes -days 365 \
    -newkey rsa:2048 \
    -keyout /etc/nginx/ssl/nginx.key \
    -out /etc/nginx/ssl/nginx.crt \
    -subj "/C=ES/ST=Madrid/L=Madrid/O=NGINX/CN=localhost"

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]
