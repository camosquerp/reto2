
# Reto2-Top_telematica
# info de la materia: ST0263

# Estudiante(s):
## Carlos Andres Mosquera, camosquerp@eafit.edu.co


# Profesor: 
## Edwin Nelson Monotya Munera, emontoya@eafit.edu.co




# 1. breve descripción de la actividad
Este proyecto consiste en construir un sistema de administración de archivos usando microservicios. Hay dos microservicios principales: mserv1 para listar archivos y mserv2 para buscar archivos. Estos microservicios se comunican mediante gRPC y, si hay problemas, a través de RabbitMQ. Se ha creado un API Gateway con Flask para que los usuarios puedan listar y buscar archivos de manera sencilla a través de endpoints de API REST.

# 1.1. Que aspectos cumplió o desarrolló de la actividad propuesta por el profesor (requerimientos funcionales y no funcionales)
Lanzamiento de instancia de AWS.
Configuracion de reglas de seguridad de la instacia 

# 1.2. Que aspectos NO cumplió o desarrolló de la actividad propuesta por el profesor (requerimientos funcionales y no funcionales)
No se logro la implementacion de la API Gateway para manejar las solicitudes de los usarios 
No hya interaccion de los microservicios

# 2. información general de diseño de alto nivel, arquitectura, patrones, mejores prácticas utilizadas.
Descripción del Sistema:
El sistema es una solución de administración de archivos basada en microservicios, diseñada para permitir a los usuarios listar y buscar archivos en un directorio específico.

## Arquitectura:
El sistema sigue una arquitectura de microservicios, donde los componentes se dividen en unidades más pequeñas e independientes. Los microservicios mserv1 y mserv2 gestionan la funcionalidad de listar y buscar archivos respectivamente.

## Comunicación entre Microservicios:
La comunicación entre microservicios se realiza a través de gRPC, un protocolo de comunicación de alto rendimiento. Si hay problemas en la comunicación gRPC, se utiliza RabbitMQ como middleware MOM para enviar y recibir mensajes asincrónicos entre microservicios.

## API Gateway:
Se ha implementado un API Gateway utilizando Flask, que proporciona endpoints de API REST para que los usuarios interactúen con el sistema. El API Gateway maneja las solicitudes de los usuarios y se encarga de dirigir las peticiones a los microservicios correspondientes.

## Microservicio mserv1:
Funcionalidad: Listar archivos en un directorio específico.
Comunicación: Utiliza gRPC para recibir solicitudes de listado de archivos.
Manejo de Fallos: Si la comunicación gRPC falla, envía solicitudes a través de RabbitMQ.


## Microservicio mserv2:
Funcionalidad: Buscar archivos en un directorio basándose en un patrón.
Comunicación: Utiliza gRPC para procesar solicitudes de búsqueda de archivos.
Manejo de Fallos: En caso de problemas de comunicación gRPC, utiliza RabbitMQ para manejar las solicitudes.

# 3. Descripción del ambiente de desarrollo y técnico
## Lenguaje de programacion 
Para este proyecto se usa el legnuaje de programacion pyhton 

## librerias 
grpc,flask,pika 
blinker==1.6.2
click==8.1.7
colorama==0.4.6
Flask==2.3.2
grpcio==1.57.0
grpcio-tools==1.57.0
importlib-metadata==6.8.0
itsdangerous==2.1.2
Jinja2==3.1.2
MarkupSafe==2.1.3
pika==1.3.2
protobuf==4.24.1
python-dotenv==1.0.0
Werkzeug==2.3.7
zipp==3.16.2

# Referencias:

https://github.com/protocolbuffers/protobuf/releases
https://medium.com/@LogeshSakthivel/installing-protobuf-compiler-protoc-536e7770e13b
https://www.youtube.com/watch?v=WB37L7PjI5k&pp=ygULZ3JwYyBweXRob24%3D
https://subscription.packtpub.com/book/programming/9781783981526/11/ch11lvl1sec61/pika

