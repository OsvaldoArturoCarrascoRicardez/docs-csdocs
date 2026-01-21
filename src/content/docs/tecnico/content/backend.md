---
title: Content Backend
---

<p align="center">
<img src="https://laravel.com/img/logomark.min.svg" alt="Laravel" height="50">
<img src="https://laravel.com/img/logotype.min.svg" alt="Laravel" height="30">
</p>

## 📋 Tabla de Contents

- [Descripción del Proyecto](#-descripción-del-proyecto)
- [Características](#-características)
- [Requisitos Previos](#-requisitos-previos)
- [Instalación Rápida](#-instalación-rápida)
- [Configuración Detallada](#-configuración-detallada)
- [Configuración de Dominios](#-configuración-de-dominios)
- [Comandos Útiles](#-comandos-útiles)
- [Solución de Problemas](#-solución-de-problemas)

---

## 📖 Descripción del Proyecto

**Content Light Back** es un sistema de gestión documental basado en Laravel 11 que funciona como aplicación cliente del
sistema **Core**. Diseñado para la administración eficiente de documentos, usuarios y múltiples dominios en una
arquitectura modular y escalable.

---

## ✨ Características

- ✅ **Autenticación OAuth2** integrada con sistema Core
- ✅ **Gestión documental** completa (subida, categorización, búsqueda)
- ✅ **Sistema multi-dominio** opcional
- ✅ **API RESTful** para integraciones externas
- ✅ **Panel administrativo** intuitivo
- ✅ **Gestión de permisos** granular por roles
- ✅ **Soporte Docker** para entornos consistentes
- ✅ **Base de datos MySQL** con soporte para múltiples esquemas
- ✅ **Caché Redis** para mejor rendimiento
- ✅ **Frontend moderno** con Angular 18

---

## ⚙️ Requisitos Previos

### Software Requerido

- **Docker** y **Docker Compose** (recomendado)
- **Git** para control de versiones
- **PHP 8.2+** (para desarrollo sin Docker)
- **Composer** (gestor de dependencias PHP)
- **Node.js 20+** y **Yarn** (para assets frontend)

### Credenciales de Acceso

- Acceso al repositorio de Bitbucket
- Credenciales de MySQL
- Proyecto **Core** configurado y funcionando

---

## 🚀 Instalación Rápida

### 1. Clonar el Repositorio

```bash
cd /var/www/html/
git clone git@bitbucket.org:csdocs/content-light-back.git
cd content-light-back
```

### 2. Configurar Entorno

```bash
# Copiar archivo de entorno
cp .env.example .env

# Configurar permisos
chmod -R 775 storage bootstrap/cache
```

### 3. Configurar Docker

```bash
# Iniciar contenedores
docker-compose up -d

# Entrar al contenedor PHP
docker exec -it content_php bash
```

### 4. Instalar Dependencias

```bash
# Instalar dependencias PHP
composer install
```

### 5. Configurar Base de Datos (unica si aplica)

```sql
-- Crear base de datos manualmente
CREATE
DATABASE content_light;
```

### 6. Ejecutar Link de Archivos

```bash
php artisan storage:link
```

### 7. Crear Usuario Administrador

```bash
php artisan cont:user:create-root
php artisan create:csdocs # agregar archivos logo y manual por defult
```

---

## 🔧 Configuración Detallada

### Paso 1: Configuración del Sistema Core (Requisito Previo)

Antes de configurar Content Light Back, asegúrate de tener el sistema **Core** funcionando. Sigue las instrucciones en
el README de `csdocs-core`.

### Paso 2: Configurar Archivo .env

### Paso 3: Copiar Credenciales OAuth desde Core

```bash
# Copiar las llaves OAuth del sistema Core
cp ../csdocs-core/storage/oauth-private.key storage/
cp ../csdocs-core/storage/oauth-public.key storage/
```

---

## 🌐 Configuración de Dominios

El sistema soporta dos modos de operación:

### 🔸 **Modo Single Dominio** (Recomendado para inicio)

```ini
# En tu .env configurar:
DB_DATABASE = content_light
```

Crear manualmente la base de datos en MySQL.

### 🔸 **Modo Multi-Dominio** (Configuración avanzada)

```ini
# Usar la misma base de datos de Core para gestión de dominios
DB_DATABASE = csdocs_core
DB_CORE_DATABASE = csdocs_core
```

**Nota:** En modo multi-dominio, el sistema creará automáticamente bases de datos para cada nuevo dominio registrado a
través del panel administrativo.

---

## 🛠️ Comandos Útiles

### Desarrollo

```bash
# Limpiar cachés
php artisan optimize:clear

# Ver rutas disponibles
php artisan route:list
```

### Mantenimiento

```bash
# Ver logs
tail -f storage/logs/laravel.log
```

---

## 🔍 Solución de Problemas

### Problema: Error "Class not found"

```bash
composer dump-autoload
php artisan optimize:clear
```

### Problema: Permisos denegados

```bash
sudo chown -R $USER:www-data storage bootstrap/cache
sudo chmod -R 775 storage bootstrap/cache
```

### Problema: Error OAuth

```bash
# Verificar que las llaves existan
ls -la storage/oauth-*.key
```

---

## 📊 Estado del Proyecto

- **Versión:** 1.0.0
- **Laravel:** 11.x
- **PHP:** 8.2.x
- **MySQL:** 8.1.x
- **Entorno:** Docker

---

## 📝 Notas Importantes

⚠️ **IMPORTANTE:**

- Este proyecto depende del sistema **Core** para funcionar correctamente
- Las credenciales OAuth deben coincidir entre ambos sistemas
- En modo producción, configurar `APP_DEBUG=false`
- Realizar backups regulares de la base de datos

---

**Desarrollado por:** [CSDocs]  
**Última actualización:** Diciembre 2023  
**Documentación:** Este archivo README.md

---

<p align="center">
✨ <strong>Content Light Back - Sistema de Gestión Documental</strong> ✨
</p>
