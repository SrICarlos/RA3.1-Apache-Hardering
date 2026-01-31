# Práctica 5 – Mitigación de ataques DoS

## Objetivo
Mitigar ataques de denegación de servicio básicos mediante la limitación del número de peticiones permitidas por cliente.

## Implementación
Se ha configurado el módulo mod_evasive en Apache para detectar patrones de tráfico anómalos.  
El módulo bloquea temporalmente a los clientes que superan los umbrales de peticiones establecidos.

## Evidencias
- Dockerfile con la instalación y configuración de mod_evasive.
![DockerFile de Mitigacion de DOS](imagenes/DockerDOS.png)
- Registros del servidor mostrando la denegación de peticiones por exceso de solicitudes.
![Log de Comprobacion de denegacion de exceso de peticiones](imagenes/DOSlog.png)
## Conclusión
La implementación de mod_evasive permite reducir el impacto de ataques DoS simples, protegiendo la disponibilidad del servicio web.
