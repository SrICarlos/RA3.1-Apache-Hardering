FROM pps/pr3

ENV DEBIAN_FRONTEND=noninteractive

# OWASP A05 - Security Misconfiguration
# Limitar métodos HTTP y deshabilitar TRACE
RUN echo 'TraceEnable Off\n\
<Directory /var/www/html>\n\
    <LimitExcept GET POST HEAD>\n\
        Require all denied\n\
    </LimitExcept>\n\
</Directory>' \
> /etc/apache2/conf-available/http-methods.conf

# Activar la configuración
RUN a2enconf http-methods

EXPOSE 80 443

CMD ["apachectl", "-D", "FOREGROUND"]
