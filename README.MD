## Licenciatura en Ingeniería en Tecnologías de la Información y Comunicación

### Área Redes Inteligentes y Ciberseguridad

### Automatización de Infraestructura Digital I

#### Unidad 1. Entornos de desarrollo en la automatización de redes

**Docente:** Eric Domenzain Morales  
**Tema:** Instrumento de evaluación  
**Nombre del alumno:** Kevin Cabrera Luna  
**Número de control:** 1222100487
**Grupo:** GIRI5091

*Dolores Hidalgo Cuna de la Independencia Nacional, Guanajuato a miércoles 11 de junio del 2025.*

---

# Índice

* [Introducción](#introducción)
* [Desarrollo](#desarrollo)

  * [Descripción de las herramientas utilizadas para automatización](#descripción-de-las-herramientas-utilizadas-para-automatización)

    * [Docker Engine](#docker-engine)
    * [Docker Compose](#docker-compose)
    * [Docker y Swagger (OpenAPI)](#docker-y-swagger-openapi)
  * [Procedimiento de instalación](#procedimiento-de-instalación)

    * [Instalación técnica de herramientas](#instalación-técnica-de-herramientas)
    * [Instalación técnica de Docker en Ubuntu](#instalación-técnica-de-docker-en-ubuntu)
    * [Instalación técnica de Git](#instalación-técnica-de-git)
* [Evidencia de pruebas de verificación](#evidencia-de-pruebas-de-verificación)
* [Comandos utilizados](#comandos-utilizados)
* [Conclusión](#conclusión)
* [Bibliografía](#bibliografía)

---

# Introducción

El siguiente documento presenta el procedimiento de instalación, configuración y despliegue de un entorno de desarrollo para automatización de redes, utilizando herramientas modernas como Docker, Git y Visual Studio Code sobre Ubuntu. Se expone cómo estas herramientas permiten establecer entornos eficientes, replicables y fácilmente administrables, facilitando tanto el desarrollo como la operación de sistemas distribuidos.

Este proyecto se centra en el uso de Docker para contenerizar una aplicación compuesta por un frontend (servido con Nginx), un backend en Node.js y servicios auxiliares como MySQL y PhpMyAdmin. Además, se empleó Docker Compose para orquestar todos los servicios, integrándolos y ejecutándolos en conjunto de forma sencilla. También se contempla el uso de Swagger como herramienta para documentación de APIs, y se incluye evidencia de funcionamiento.

---

# Desarrollo

## Descripción de las herramientas utilizadas para automatización

### Docker Engine

Docker Engine es el motor principal que permite construir y correr contenedores. En este proyecto se usó para contenerizar servicios como Node.js, MySQL y PhpMyAdmin, facilitando su despliegue sin depender del sistema anfitrión.

### Docker Compose

Docker Compose simplificó la orquestación de múltiples contenedores. Se utilizó para definir los servicios en un único archivo YAML (`docker-compose-kcl.yml`), permitiendo levantar toda la infraestructura con un solo comando.

### Docker y Swagger (OpenAPI)

Swagger fue considerado para documentar APIs RESTful del backend. Aunque no se integró directamente en este entorno, se dejó preparado para que en siguientes fases se incluya documentación de endpoints.

---

## Procedimiento de instalación

### Instalación técnica de herramientas

#### Visual Studio Code

Se descargó desde su sitio oficial y se instalaron extensiones útiles como Docker, YAML y Git. También se usó para editar los archivos `Dockerfile`, `.yml` y el código del backend.

#### Plugins utilizados:

* Docker
* GitLens
* Prettier
* ESLint

---

### Instalación técnica de Docker en Ubuntu

Se siguieron los pasos oficiales de Docker para instalar Docker Engine y Docker Compose Plugin. Posteriormente, se configuró el entorno para ejecutar Docker sin `sudo`.

### Instalación técnica de Git

Git se instaló mediante `apt` y se configuraron nombre de usuario y correo para conectar con GitHub. Se creó el repositorio: [https://github.com/edersg19/instrumento-auto-egsg](https://github.com/edersg19/instrumento-auto-egsg).

---

# Evidencia de pruebas de verificación

## Imagen "hello-world"

Se ejecutó el contenedor de prueba:

```bash
docker run hello-world
```

Resultado exitoso, indicando que Docker estaba bien instalado.

## Ejecución de un archivo yml

Se ejecutó:

```bash
docker compose -f docker-compose-kcl.yml up --build
```

Esto levantó los servicios:

* PhpMyAdmin: [http://localhost:9090](http://localhost:9090)
* Backend Node.js: [http://localhost:8080](http://localhost:8080)
* Frontend Nginx: [http://localhost](http://localhost)

Todos los servicios funcionaron correctamente.

---

# Comandos utilizados

```bash
# Instalación y verificación de Docker
sudo apt install docker.io -y
docker --version

# Permisos para ejecutar Docker sin sudo
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker

# Ejecutar imagen de prueba
docker run hello-world

# Inicializar y construir el entorno
docker compose -f docker-compose-kcl.yml up --build

# Ver contenedores en ejecución
docker ps

# Entrar a un contenedor (ej. frontend)
docker exec -it sistema-ventas-front sh

# Ver estructura de carpetas
ls -l /usr/share/nginx/html

# Descargar imagen manual si falla la descarga por red
docker pull node:18.17.1-alpine
```

---

# Conclusión

Este entorno de automatización demuestra cómo Docker y sus herramientas asociadas facilitan la creación de sistemas replicables y fácilmente administrables. Gracias a Docker Compose, se logró orquestar una arquitectura de múltiples servicios de forma sencilla. Además, el uso de Visual Studio Code y Git integrados con Docker potencia el flujo de desarrollo.

Se realizaron pruebas funcionales que confirman el correcto funcionamiento del entorno, evidenciado con la ejecución de `hello-world` y el levantamiento de servicios vía Compose. Este entorno sienta las bases para trabajar con microservicios, DevOps y CI/CD.

---

# Bibliografía

1. Docker. *Install Docker Engine on Ubuntu*. Docker Documentation. [https://docs.docker.com/engine/install/ubuntu/](https://docs.docker.com/engine/install/ubuntu/)
2. Docker. *Post-installation steps for Linux*. [https://docs.docker.com/engine/install/linux-postinstall/](https://docs.docker.com/engine/install/linux-postinstall/)
3. Microsoft. *Download Visual Studio Code*. [https://code.visualstudio.com/](https://code.visualstudio.com/)
4. Git SCM. *Downloads*. [https://git-scm.com/downloads](https://git-scm.com/downloads)
5. GitHub. *Git configuration*. [https://docs.github.com/en/get-started/getting-started-with-git/configuring-git](https://docs.github.com/en/get-started/getting-started-with-git/configuring-git)
6. Docker Compose. *Overview*. [https://docs.docker.com/compose/](https://docs.docker.com/compose/)
