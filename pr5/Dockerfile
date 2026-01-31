FROM pps/pr4

ENV DEBIAN_FRONTEND=noninteractive

# Instalar mod_evasive
RUN apt update && \
    apt install -y libapache2-mod-evasive && \
    apt clean && rm -rf /var/lib/apt/lists/*

# Configuración agresiva de mod_evasive (DoS)
RUN printf "<IfModule mod_evasive20.c>\n\
DOSHashTableSize    3097\n\
DOSPageCount        2\n\
DOSSiteCount        5\n\
DOSPageInterval     1\n\
DOSSiteInterval     1\n\
DOSBlockingPeriod   20\n\
</IfModule>\n" \
> /etc/apache2/mods-available/evasive.conf

# Activar el módulo
RUN a2enmod evasive

EXPOSE 80 443

CMD ["apachectl", "-D", "FOREGROUND"]
