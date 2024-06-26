# VOLUMEN TIPO HOST
Un volumen host (o bind mount) es un tipo de volumen donde se monta un directorio o archivo específico del sistema de archivos del host en un contenedor.

```
docker run -d --name <nombre contenedor> -v <ruta carpeta host>:<ruta carpeta contenedor> <imagen>
```

### Crear un volumen tipo host con la imagen nginx:alpine, mapear todos por puertos, para la ruta carpeta host: directorio en donde se encuentra la carpeta html en tu computador y para la ruta carpeta contenedor: /usr/share/nginx/html esta ruta se obtiene al revisar la documentación
![Volúmenes](imagenes/volumen-host.PNG)
# COMPLETAR CON EL COMANDO
docker run -d --name mynginx -p 8080:80 -v $(pwd)/html:/usr/share/nginx/html nginx:alpine


### ¿Qué sucede al ingresar al servidor de nginx?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA
Al ingresar al servidor de nginx, se muestra el contenido de la carpeta html del host.

### ¿Qué pasa con el archivo index.html del contenedor?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA
El archivo index.html del contenedor se sobrescribe con el archivo index.html del directorio montado del host.

### Ir a https://html5up.net/ y descargar un template gratuito, descomprirlo dentro de nginx/html
### ¿Qué sucede al ingresar al servidor de nginx?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA
Al ingresar al servidor de nginx, se muestra el nuevo template descargado desde HTML5 UP.

### Eliminar el contenedor
# COMPLETAR CON EL COMANDO
docker rm -f mynginx

### ¿Qué sucede al crear nuevamente el mismo contenedor con volumen de tipo host a los directorios definidos anteriormente?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA
El nuevo contenedor nginx mostrará el mismo contenido HTML del host, ya que el volumen de tipo host mapea el mismo directorio.

### ¿Qué hace el comando pwd?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA
El comando pwd imprime el directorio de trabajo actual.


### Volumen tipo host usando PWD y PowerShell
```
docker run -d --name mynginx --publish 8080:80 -v ${PWD}/html:/usr/share/nginx/html nginx:alpine

```

### Volumen tipo host usando PWD (Git Bash)

```
docker run -d --name mynginx --publish 8080:80 -v $(pwd -W)/html:/usr/share/nginx/html nginx:alpine

```

### Volumen tipo host usando PWD (en Linux)

```
docker run -d --name mynginx --publish 8080:80 -v $(pwd)/html:/usr/share/nginx/html nginx:alpine

```