# Práctica 2 – Hardening básico de Apache

## Objetivo
Configurar un servidor Apache con medidas básicas de seguridad, incluyendo HTTPS y cabeceras de seguridad, con el objetivo de reducir la superficie de ataque del servicio web.

## Implementación
Se ha desplegado un servidor Apache dentro de un contenedor Docker.  
Se ha configurado HTTPS mediante un certificado autofirmado y se han añadido cabeceras de seguridad como HSTS y Content-Security-Policy.  
Además, se han deshabilitado funcionalidades innecesarias para evitar la exposición de información sensible.

## Evidencias
- Dockerfile con la configuración del servidor Apache.
![DockerFile del CSP](imagenes/DockerCSP.png)
- Comprobación del funcionamiento mediante una petición HTTPS con curl.
![Comprobacion del CSP](imagenes/CurlCSP.png)
## Conclusión
Con esta práctica se ha conseguido desplegar un servidor Apache más seguro, aplicando medidas básicas de hardening que protegen frente a ataques comunes y mejoran la confidencialidad de las comunicaciones.
