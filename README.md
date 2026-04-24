# MiniScrum Distribuido

## Objetivo

Explicar brevemente que hace la aplicacion.

## Arquitectura

Navegador -> Node Gateway -> PHP API -> MySQL
Navegador -> Node Gateway -> Python ML API

## Servicios

- gateway: frontend y API Gateway.
- php-api: CRUD de tareas.
- python-ml: prediccion de puntos Scrum.
- mysql: base de datos relacional.

## Endpoints principales

- GET /api/tasks
- POST /api/tasks
- PUT /api/tasks/:id/status
- POST /api/predict

## Base de datos

Tabla principal: tasks.

## Como ejecutar localmente

docker compose up --build

## URL desplegada

Pegar aqui la URL de Dockploy.

## Evidencias

Agregar capturas de:
- aplicacion funcionando
- tareas guardadas
- contenedores activos
- repositorio con commits

## Retrospectiva

Que salio bien: Construcción de la aplicación en local

Que fue dificil: Hacer el Deployment

Que mejoraria: Revisar errores desde el inicio 

1. Por que el navegador no se conecta directamente a MySQL?
MySQL no debe estar expuesto a internet. La API actúa de intermediario y protege la base de datos.
2. Que ventaja tiene separar el servicio PHP del servicio Python?
Que se pueden mejorar y escalar de forma independiente.
3. Que funcion cumple el API Gateway?
Recibe todas las peticiones del navegador y las redirige al servicio
4. Que pasaria si el servicio Python deja de funcionar?
Fallaría la predicción de puntos
5. Que diferencia hay entre ejecutar localmente con Docker Compose y desplegar en Dockploy?
Localmente sólo yo puedo acceder mientras que desplegado otros pueden acceder.
6. Que parte del sistema representa la capa de datos?
MySQL
7. Que parte representa la capa de presentacion?
Navegador
8. Que parte representa la logica de negocio?
Lo de PHP-api y python