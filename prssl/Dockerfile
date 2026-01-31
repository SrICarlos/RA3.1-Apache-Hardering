FROM pps/pr5

# Activar módulos necesarios
RUN a2enmod ssl rewrite

# Configuración de redirección HTTP → HTTPS
COPY ssl-redirect.conf /etc/apache2/sites-available/ssl-redirect.conf

# Activar la configuración
RUN a2ensite ssl-redirect && \
    a2dissite 000-default

EXPOSE 80 443

CMD ["apachectl", "-D", "FOREGROUND"]
