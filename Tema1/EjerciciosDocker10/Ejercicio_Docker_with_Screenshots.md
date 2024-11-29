
# Ejercicio Docker - Creación y Publicación de Imágenes

## Parte 1: Creación de Imagen Personalizada Basada en Ubuntu

### Pasos

1. **Arrancar un contenedor desde la imagen `ubuntu:20.04`:**

   ```bash
   docker run -it --name mi_ubuntu_container ubuntu:20.04 bash
   ```
   [Paso 1](capturas/1.png)

2. **Dentro del contenedor, ejecutar los siguientes comandos:**

   ```bash
   apt update
   ```
   [Paso 2](capturas/2.png)

   ```bash
   apt install -y nano
   ```
   [Paso 3](capturas/3.png)

   ```bash
   apt install -y vim
   ```
   [Paso 4](capturas/4.png)

   ```bash
   apt install -y inetutils-tools
   ```
   [Paso 1](capturas/5.png)

   ```bash
   apt install -y dnsutils
   ```
   [Paso 1](capturas/6.png)
   [Paso 1](capturas/7.png)

   ```bash
   adduser usuario
   ```
   [Paso 1](capturas/8.png)

3. **Salir del contenedor:**

   ```bash
   exit
   ```
   [Paso 1](capturas/9.png)

4. **Crear una imagen basada en el contenedor:**

   ```bash
   docker commit mi_ubuntu_container ignacio/a61
   ```
   [Paso 1](capturas/10.png)

5. **Subir la imagen a DockerHub:**

   ```bash
   docker login
   ```
   [Paso 1](capturas/11,5.png)
   [Paso 1](capturas/11.png)

   ```bash
   docker push ignacio/a61
   ```
   [Paso 1](#)

---

## Parte 2: Construcción de un Dockerfile Basado en PHP

### Pasos

1. **Crear un directorio para el Dockerfile y sus recursos:**

   ```bash
   mkdir php_apache_custom
   cd php_apache_custom
   ```
   [Paso 1](#)

2. **Crear un archivo `Dockerfile` con el siguiente contenido:**

   ```dockerfile
   FROM php:7.4-apache

   RUN apt update && apt install -y nano git

   COPY index.html /var/www/html/index.html
   COPY info.php /var/www/html/info.php
   ```
   [Paso 1](#)

3. **Crear el archivo `index.html`:**

   ```html
   <html>
       <body>
           <h1>HOLA SOY NACHO</h1>
       </body>
   </html>
   ```
   [Paso 1](#)

 .

4. **Crear el archivo `info.php`:**

   ```php
   <?php phpinfo(); ?>
   ```
   [Paso 1](#)

5. **Construir la imagen:**

   ```bash
   docker build -t ignacio/a62 .
   ```
   [Paso 1](#)

6. **Subir la imagen a DockerHub:**

   ```bash
   docker login
   ```
   [Paso 1](#)

   ```bash
   docker push ignacio/a62
   ```
   [Paso 1](#)
