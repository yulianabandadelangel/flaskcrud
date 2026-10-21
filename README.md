# Flask CRUD — Contenerizado

CRUD de contactos en Flask + MySQL, empaquetado en Docker.

## Requisitos

- Docker y Docker Compose instalados

## Levantar el proyecto

Primera vez (construye la imagen y crea la base de datos):

```bash
docker-compose up --build
```

Siguientes veces:

```bash
docker-compose up
```

Parar los servicios:

```bash
docker-compose stop
```

La app queda disponible en: <http://localhost:8080>

## Servicios

- **mysql** → MySQL 8.0 en el puerto `3306`. El script `sql/db.sql` se ejecuta solo la primera vez para crear la base `flaskcrud` y la tabla `contacts`.
- **pythonapp** → Flask corriendo en el puerto `8080`, conectado a MySQL por el hostname `mysql` (red interna de Docker Compose).

## Variables de entorno

Las variables se pasan desde `docker-compose.yml`. Si quieres correr fuera de Docker, copia `.env.example` a `.env` y ajusta los valores:

```bash
cp .env.example .env
```
