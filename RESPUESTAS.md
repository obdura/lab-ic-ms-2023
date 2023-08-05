# Respuestas

Indica tu nombre a continuación: 

Por cada etapa agrega una sección abajo y escribe las respuestas a las preguntas de cada etapa.

## ETAPA 1

Escribe respuestas de la etapa 1 acá

¿Cuál es la diferencia entre los archivos con el verbo `Create` con los archivos con el verbo `Add`?
* Los archivos con el prefijo `create` crean las tablas
* Los archivos con el prefijo `add` agregan datos a las tablas.

¿Cómo se llama el servicio que se declara en el archivo `docker-compose.yml`?
* `flyway`

¿Cuál es el comando que se ejecuta en el servicio declarado?
* `-locations=filesystem:/flyway/sql -connectRetries=60 migrate`


## ETAPA 2

Escribe respuestas de la etapa 2 acá

¿Qué pasa si cambias el nombre del servicio de `postgres` a `db`? ¿Qué otros cambios tendrías que hacer?

El servicio adquiere otro nombre, y debería cambiarse el contenido del `depends_on` en el servicio flyway, del siguiente modo:
```
depends_on:
  - db
```
...

## ETAPA 3

Revisa el archivo `movies-api/Dockerfile`.

¿Qué te llama la atención?

* Hay una etapa de building (compilacion) y despliegue (deployment). Cada una corresponde a una imagen distinta.

Revisa el archivo `docker-compose.yml`.

¿Cómo se relacionan el archivo `docker-compose.yml` y el archivo `movies-api/Dockerfile`?

* El servicio `movies-api` descrito en el archivo `docker-compose` _invoca_ al dockerfile de la carpeta `movies-api`, creando una imagen a partir de este elemento. Por otro lado, el servicio `movies-api` *utiliza* al servicio postgres a traves de la dependencia indicada en `dependes_on`.

¿Qué crees que hace el atributo `context` debajo de `build` (está en la linea 6 del archivo `docker-compose.yml`)?

* Señala la ruta del directorio donde se ubica el dockerfile definiendo un contexto.
