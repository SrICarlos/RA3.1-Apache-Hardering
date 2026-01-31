FROM pps/pr1

ENV DEBIAN_FRONTEND=noninteractive

# Activar módulos necesarios
RUN a2enmod headers ssl

# Reducir información expuesta del servidor
RUN echo "ServerTokens Prod\nServerSignature Off" \
    > /etc/apache2/conf-available/server-info.conf

RUN a2enconf server-info

# Deshabilitar autoindex
RUN a2dismod -f autoindex

# Crear certificado autofirmado
RUN mkdir /etc/apache2/ssl && \
    openssl req -x509 -nodes -days 365 \
    -newkey rsa:2048 \
    -keyout /etc/apache2/ssl/apache.key \
    -out /etc/apache2/ssl/apache.crt \
    -subj "/C=ES/ST=Valencia/L=Valencia/O=Prueba/OU=DAW/CN=localhost"

# Configuración SSL
RUN echo '<VirtualHost *:443>\n\
    ServerName localhost\n\
    DocumentRoot /var/www/html\n\
    SSLEngine on\n\
    SSLCertificateFile /etc/apache2/ssl/apache.crt\n\
    SSLCertificateKeyFile /etc/apache2/ssl/apache.key\n\
</VirtualHost>' > /etc/apache2/sites-available/default-ssl.conf

RUN a2ensite default-ssl

# HSTS + CSP
RUN echo 'Header always set Strict-Transport-Security "max-age=31536000; includeSubDomains"\n\
Header always set Content-Security-Policy "default-src '\''self'\''"' \
> /etc/apache2/conf-available/security-headers.conf

RUN a2enconf security-headers

# Exponer puertos
EXPOSE 80 443

CMD ["apachectl", "-D", "FOREGROUND"]
