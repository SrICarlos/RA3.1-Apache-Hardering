# Práctica 4 – Mitigación de riesgos OWASP Top 10

## Objetivo
Aplicar medidas de seguridad alineadas con las recomendaciones del OWASP Top 10 para reducir riesgos comunes en aplicaciones web.

## Implementación
Dado que las prácticas se desarrollan de forma incremental, varias medidas ya estaban implementadas en prácticas anteriores.  
En esta práctica se ha reforzado la configuración del servidor limitando los métodos HTTP permitidos, reduciendo así la superficie de ataque.

## Evidencias
- Dockerfile con la configuración de métodos HTTP permitidos.
![DockerFile del OWASP](imagenes/DockerOWASP.png)
- Prueba mediante curl mostrando el bloqueo de métodos no autorizados.
![Comprobacion del OWASP](imagenes/CurlOWASP.png)
## Conclusión
Las medidas aplicadas permiten mitigar riesgos asociados al OWASP Top 10, mejorando el control sobre las peticiones HTTP aceptadas por el servidor.
