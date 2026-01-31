FROM pps/pr2

ENV DEBIAN_FRONTEND=noninteractive

# Instalar ModSecurity + CRS
RUN apt update && \
    apt install -y libapache2-mod-security2 modsecurity-crs && \
    apt clean && rm -rf /var/lib/apt/lists/*

# Activar ModSecurity en modo bloqueo
RUN mv /etc/modsecurity/modsecurity.conf-recommended \
       /etc/modsecurity/modsecurity.conf

RUN sed -i 's/SecRuleEngine DetectionOnly/SecRuleEngine On/' \
    /etc/modsecurity/modsecurity.conf

# NO crear includes extra (Debian ya los carga)
# NO a2enconf modsecurity
# NO duplicar CRS

EXPOSE 80 443

CMD ["apachectl", "-D", "FOREGROUND"]
