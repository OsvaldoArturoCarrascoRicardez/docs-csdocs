---
title: Core Backend
---

# Instalación y configuración de CORE

## **`Backend`** con Laravel 11

**Primero:**

Clona el repositorio en la carpeta de projects

```bash
cd /var/www/html/
```

Clona el repositorio

```bash
git clone git@bitbucket.org:csdocs/csdocs-core.git
```

Nos cambiamos de rama sea el caso si no permanecemos en master

```bash
cd csdocs-core

git checkout origin develop
```

**Asignación de permisos**

```bash
sudo chmod 777 bootstrap
sudo chmod 777 bootstrap/cache
sudo chmod 777 storage/app
sudo chmod 777 storage/framework
sudo chmod 777 storage/framework/views
sudo chmod 777 storage/framework/cache
sudo chmod 777 storage/framework/cache/data
sudo chmod 777 storage/framework/sessions
sudo chmod 777 storage/framework/testing
sudo chmod 777 storage/logs
```

**Creación de archivo de log y environments**

```bash
sudo touch storage/logs/laravel.log

sudo chmod 777 storage/logs/laravel.log

sudo cp .env.example .env

sudo chmod 777 .env
```

1. **`Docker`** Entra al contenedor de MySQL con el usuario root y clave

```bash
docker exec -it mysql bash
```

- Para entrar a la consola de MySQL usa:

```bash
mysql -u root -p
```

- Dentro de la consola de MySQL ejecuta:

```bash
CREATE DATABASE csdocs_core;
exit
```

- Para salir del contenedor:

```bash
exit
```

1. Archivo .ENV

```ini
APP_URL=http://localhost.core.net
FRONT_URL='http://localhost:5200'

DB_CONNECTION=mysql
DB_HOST=core_mysql
DB_PORT=3306
DB_DATABASE=csdocs_core
DB_USERNAME=root
DB_PASSWORD=secret

REDIS_HOST=redis_core
REDIS_PASSWORD=null
REDIS_PORT=6379
```

1. **`Docker`** Instalación de Laravel, entrar al contenedor del core_csdocs ejecutando

```bash
docker exec -it php82 bash
```

1. Dentro del contenedor ejecuta:

```bash
cd core

composer install
```

1. Valida ejecutando

```bash
php artisan

php artisan --version
```

1. Ejecución de migraciones y seeders

```bash
php artisan migrate
php artisan db:seed
php artisan passport:key # Solo si no existe archivos de llaves
php artisan passport:client --personal
```

1. Crea enlaces simbólicos en storage

```bash
php artisan storage:link
```
