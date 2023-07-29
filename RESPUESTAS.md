# Respuestas

Indica tu nombre a continuación: 

Por cada etapa agrega una sección abajo y escribe las respuestas a las preguntas de cada etapa.

## ETAPA 1

Escribe respuestas de la etapa 1 acá

## ETAPA 2

Escribe respuestas de la etapa 2 acá

¿Qué pasa si cambias el nombre del servicio de `postgres` a `db`? ¿Qué otros cambios tendrías que hacer?

El servicio adquiere otro nombre, y debería cambiarse el contenido del `depends_on` en el servicio flyway, del siguiente modo:
```
depends_on:
  - db
```