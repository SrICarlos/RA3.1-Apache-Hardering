# Práctica 3.3 – Apache Hardening Best Practices

## Objetivo
Aplicar buenas prácticas de seguridad al servidor Apache siguiendo las recomendaciones del artículo de Geekflare, sin depender de configuraciones previas ni herencias entre prácticas.

## Implementación
Se ha creado una imagen Docker independiente basada en Ubuntu 22.04, donde se instala Apache y se aplican medidas de hardening como la ocultación de la versión del servidor, la desactivación del listado de directorios, la reducción del fingerprinting mediante ETags y la inclusión de cabeceras de seguridad HTTP.
![Imagen DockerFile independiente todo en uno de lo que se ha hecho hasta ahora](pps/imagenes/DockerBest.png)
## Evidencias
Se han realizado pruebas con curl para comprobar la correcta aplicación de las cabeceras de seguridad y la ocultación de información sensible del servidor.
![Imagen de comprobacion de cabeceras con curl](pps/imagenes/CurlBest.png)
## Conclusión
La configuración aplicada reduce la superficie de ataque del servidor Apache y dificulta las tareas de reconocimiento, alineándose con buenas prácticas de seguridad recomendadas.
