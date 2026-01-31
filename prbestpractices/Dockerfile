FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

# -------------------------------
# Instalación de Apache
# -------------------------------
RUN apt update && \
    apt install -y apache2 && \
    apt clean && rm -rf /var/lib/apt/lists/*

# -------------------------------
# Hardening Apache (Geekflare)
# -------------------------------

# 1) Ocultar versión y firma
RUN echo "ServerTokens Prod" >> /etc/apache2/conf-available/security.conf && \
    echo "ServerSignature Off" >> /etc/apache2/conf-available/security.conf

# 2) Desactivar listado de directorios (forma compatible)
RUN cat << 'EOF' > /etc/apache2/conf-available/hardening-directory.conf
<Directory /var/www/html>
    Options FollowSymLinks
    AllowOverride None
    Require all granted
</Directory>
EOF
RUN a2enconf hardening-directory

# 3) Cabeceras de seguridad
RUN a2enmod headers
RUN cat << 'EOF' > /etc/apache2/conf-available/hardening-headers.conf
Header always set X-Frame-Options "SAMEORIGIN"
Header always set X-XSS-Protection "1; mode=block"
Header always set X-Content-Type-Options "nosniff"
EOF
RUN a2enconf hardening-headers

# 4) Deshabilitar ETags
RUN echo "FileETag None" >> /etc/apache2/conf-available/security.conf

# -------------------------------
# Puertos y arranque
# -------------------------------
EXPOSE 80

CMD ["apachectl", "-D", "FOREGROUND"]
