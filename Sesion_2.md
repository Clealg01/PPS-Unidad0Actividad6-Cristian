# Imagenes Docker

Las imágenes Docker son plantillas de solo lectura que sirven como base para crear contenedores. Cada imagen incluye el sistema de archivos y las configuraciones necesarias para ejecutar aplicaciones, como un sistema operativo (por ejemplo, Debian) o software preinstalado. Sin embargo, cualquier cambio realizado en un contenedor creado a partir de una imagen no afecta a la imagen original, ya que esta permanece inmutable. Esto asegura consistencia y reutilización, permitiendo crear múltiples contenedores idénticos a partir de una misma imagen.

Un registro de imágenes en Docker es un componente esencial para almacenar y gestionar las imágenes creadas con el Docker Engine. Este registro puede instalarse en un servidor independiente o utilizar servicios públicos como Docker Hub. Es una herramienta fundamental para distribuir aplicaciones en entornos Docker, ya que permite compartir, descargar y gestionar imágenes de manera eficiente.

Docker Hub, ofrecido como un servicio oficial por Docker, es el registro público más utilizado y accesible. Sin embargo, Docker también permite instalar registros privados de manera gratuita en cualquier servidor, utilizando su proyecto open source.

## Contenido

- [Imagenes Docker](#imagenes-docker)
  - [Contenido](#contenido)
  - [Registros de imágenes: Docker Hub](#registros-de-imágenes-docker-hub)
  - [Gestión de imágenes](#gestión-de-imágenes)
  - [¿Cómo se organizan las imágenes?](#cómo-se-organizan-las-imágenes)
  - [Creación de contenedores desde imágenes](#creación-de-contenedores-desde-imágenes)
  - [Ejemplo: Desplegando la aplicación mediawiki](#ejemplo-desplegando-la-aplicación-mediawiki)
  - [Ejercicios](#ejercicios)


## Registros de imágenes: Docker Hub
Estructura de una imagen en Docker Hub
Las imágenes en Docker Hub o cualquier registro siguen una nomenclatura específica que facilita su identificación y gestión. Esta estructura consta de tres partes principales:

usuario/nombre:etiqueta

usuario: Representa el nombre del usuario o la organización que ha creado la imagen. Si subimos imágenes a Docker Hub, este usuario debe coincidir con la cuenta registrada. Las imágenes oficiales en Docker Hub no incluyen un prefijo de usuario.
nombre: Es un nombre significativo que identifica la imagen. Este debe ser descriptivo para que otros usuarios puedan entender fácilmente su propósito.
etiqueta: Permite versionar las imágenes, ofreciendo control sobre las distintas versiones que se generan a lo largo del tiempo. Si no se especifica una etiqueta, Docker usa por defecto latest, lo que suele asociarse a la versión más reciente o estable de la imagen.
Ejemplo de nomenclatura
Un ejemplo típico de nombre de imagen es:




## Gestión de imágenes
En Docker, las imágenes son un componente fundamental para crear y ejecutar contenedores. Antes de iniciar un contenedor, es necesario disponer de la imagen correspondiente en el registro local. Si al ejecutar el comando docker run la imagen no está disponible, Docker procederá automáticamente a descargarla desde un registro como Docker Hub. La gestión de imágenes permite realizar operaciones clave como listar, descargar, eliminar, buscar o inspeccionar imágenes, facilitando así el control sobre los recursos disponibles y utilizados en nuestro entorno Docker.

Los principales comandos serían:
- `Docker images`: Este comando muestra una lista de todas las imágenes disponibles en nuestro registro local. Proporciona información como el nombre del repositorio, la etiqueta (versión), el ID de la imagen, la fecha de creación y su tamaño:

<p align="center">
    <img src="./images/Imagenes_docker.png" alt="Listar imágenes">
    </p>
<p align="center"><em>Listar imágenes</em></p>

- `Docker pull`:Este comando descarga una imagen desde un registro remoto, como Docker Hub. Si no se especifica una etiqueta, Docker descargará la versión etiquetada como latest.



- `Docker rmi`:

- `Docker search`:

- `docker inspect`: Proporciona información detallada sobre una imagen específica, en formato JSON. Entre los datos más importantes que podemos obtener se incluyen:

    - ID y checksum de la imagen: Identificadores únicos de la imagen.
    - Puertos abiertos: Información sobre los puertos expuestos.
    - Sistema operativo y arquitectura: Detalles del entorno en el que se ejecutará la imagen.
    - Tamaño: El peso de la imagen en el disco.
    - Volúmenes: Directorios que se montan en el contenedor.
    - ENTRYPOINT: Comando o proceso que se ejecuta al iniciar el contenedor.
    - Capas: Las distintas capas que forman la imagen

<p align="center">
    <img src="./images/inspeccionar_imagen.png" alt="Inspeccionar la imagen de Ubuntu">
    </p>
<p align="center"><em>Inspeccionar la imagen de Ubuntu</em></p>





## ¿Cómo se organizan las imágenes?

imagen Crear_contenedor_desde_imagen añadir que es interactivo
imagen Visualizar_tamaño_contenedor
imagen Crear_archivo_ver_tamaño_ahora
imagen Capas_latest

## Creación de contenedores desde imágenes

Imagen Crear_con_comando_en_creacion
Imagen Servidor_htttp_80
Eliminar_contenedores_no_activos (no borra las imagenes, por lo que siguen ocupando espacio)

## Ejemplo: Desplegando la aplicación mediawiki

Imagen Descargar_imagen
Imagen Correr_imagen_p8081 (debe ser en un puerto libre claramente)

## Ejercicios