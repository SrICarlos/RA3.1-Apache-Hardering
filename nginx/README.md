# Servidor NGINX Seguro

## Objetivo
Desplegar un servidor NGINX como alternativa a Apache, aplicando medidas básicas de seguridad y hardening.

## Implementación
Se ha configurado un servidor NGINX dentro de un contenedor Docker.  
Se ha habilitado HTTPS mediante un certificado autofirmado y se han añadido cabeceras de seguridad como HSTS y CSP.  
Además, se ha ocultado la versión del servidor para evitar la exposición de información sensible.

## Evidencias
- Dockerfile con la configuración del servidor NGINX.
![DockerFile del Nginx](imagenes/DockerNginx.png)
- Archivo de configuracion de NGINX.
![Archivo de configuracion de NGINX](imagenes/Nginx.png)
- Petición HTTPS realizada con curl mostrando las cabeceras de seguridad configuradas.
![Curl de comprobacion de NGINX](imagenes/CurlNginx.png)
## Conclusión
El servidor NGINX configurado cumple con las medidas básicas de seguridad requeridas, proporcionando un servicio web seguro y correctamente endurecido.
