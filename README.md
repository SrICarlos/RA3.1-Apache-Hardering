# 📘 Prácticas de Seguridad en Servidores Web  
## Apache y Nginx con Docker

Este repositorio contiene el conjunto de prácticas realizadas para la asignatura, centradas en la **configuración, securización y hardening de servidores web** utilizando **Docker** como entorno de despliegue.

Las prácticas se han organizado siguiendo los **apartados 3.1, 3.2 y 3.3**, aplicando un enfoque progresivo y práctico sobre **Apache** y **Nginx**.

---

## 📌 Estructura general de las prácticas

### 🔹 Punto 3.1 – Securización del servidor web (Apache y Nginx)

Las prácticas **PR1 a PR5** corresponden al **punto 3.1**, donde se trabaja principalmente sobre **Apache**, aplicando diferentes medidas de seguridad de forma incremental:

- **PR1** – Instalación básica de Apache en un contenedor Docker.
- **PR2 / PR3** – Configuración inicial de seguridad y despliegue de Apache en Docker.
- **PR4** – Implementación de mecanismos de protección como cabeceras de seguridad y WAF (ModSecurity + OWASP CRS).
- **PR5** – Protección frente a ataques de denegación de servicio (DoS) mediante módulos específicos como `mod_evasive`.

Cada práctica añade una capa adicional de seguridad, permitiendo observar la evolución del servidor desde una configuración básica hasta una configuración más robusta frente a ataques comunes.

#### 🔸 Nginx

Dentro de este mismo punto 3.1 se incluye también una práctica específica con **Nginx**, que se mantiene separada de Apache debido a que:

- Utiliza un servidor web distinto.
- Su configuración y filosofía difieren notablemente de Apache.
- Se gestiona mediante ficheros de configuración propios (`nginx.conf`).

Por este motivo, la práctica de Nginx se encuentra identificada con un nombre distinto y no hereda directamente de las prácticas de Apache.

---

### 🔹 Punto 3.2 – Certificados digitales y HTTPS (SSL/TLS)

En este apartado se desarrolla una práctica específica centrada en la **seguridad de las comunicaciones**, donde se configura:

- HTTPS mediante certificados SSL/TLS.
- Redirección automática de tráfico HTTP a HTTPS.
- Verificación del correcto funcionamiento mediante herramientas como `curl`.

Esta práctica se aborda de forma independiente, ya que su objetivo principal es garantizar la **confidencialidad e integridad de las comunicaciones**, más allá de la seguridad interna del servidor.
Ademas que las practicas del apartado 3.1 ya cuentan con certificados autofirmados.

---

### 🔹 Punto 3.3 – Apache Hardening Best Practices

El apartado 3.3 se centra en la aplicación de **buenas prácticas de hardening** recomendadas para servidores Apache, siguiendo guías reconocidas como la de Geekflare.

En esta práctica se consolidan y refuerzan conceptos trabajados previamente, aplicando medidas como:

- Ocultación de información del servidor.
- Desactivación del listado de directorios.
- Reducción del fingerprinting del servidor.
- Inclusión de cabeceras de seguridad adicionales.
- Organización modular de la configuración de Apache.

Aunque muchas de estas medidas ya se habían trabajado parcialmente en prácticas anteriores, en este punto se aplican de forma **estructurada, consciente y justificada**, creando una imagen Docker unica en vez de ir añadiendo las mejoras de forma incremental.

---

## 🧠 Enfoque y metodología

Las prácticas se han desarrollado con los siguientes objetivos:

- Aplicar medidas reales de seguridad en servidores web.
- Comprender el impacto de cada configuración mediante pruebas prácticas.
- Utilizar Docker para garantizar entornos reproducibles.
- Diferenciar claramente los objetivos de cada apartado del temario.
- Mantener prácticas independientes cuando el contexto lo requiere.

---

## ✅ Conclusión

Este repositorio refleja un recorrido completo por las principales técnicas de seguridad aplicables a servidores web, desde la instalación básica hasta el hardening avanzado, pasando por la protección de las comunicaciones y la mitigación de ataques comunes.

La organización por prácticas y apartados facilita la comprensión del proceso y permite evaluar cada objetivo de forma clara e independiente.
