---
title: Archivística Backend
---

## 📋 Tabla de Contenidos

- [Descripción del Proyecto](#-descripción-del-proyecto)
- [Características](#-características)
- [Requisitos Previos](#-requisitos-previos)
- [Instalación Rápida](#-instalación-rápida)
- [Configuración Detallada](#-configuración-detallada)
- [Configuración de Dominios](#-configuración-de-dominios)
- [Gestión de Queues (Colas)](#-gestión-de-queues-colas)
- [Comandos Útiles](#-comandos-útiles)
- [Solución de Problemas](#-solución-de-problemas)

---

## 📖 Descripción del Proyecto

**Archivística BackEnd** es un sistema integral de gestión documental y archivonomía desarrollado con Laravel 10,
diseñado para cumplir con los lineamientos de la **Ley General de Archivos**.

Funciona como una aplicación cliente vinculada al ecosistema **Core**, permitiendo administrar el ciclo de vida de los
documentos (Trámite, Concentración e Histórico), la clasificación archivística, transferencias y préstamos de
expedientes de manera eficiente y segura.

---

## ✨ Características

- ✅ **Cumplimiento Legal**: Estructura de documentos y expedientes basada en la Ley de Archivos.
- ✅ **Gestión de Ciclo de Vida**: Control de fases de archivo (Trámite, Concentración, Histórico).
- ✅ **Autenticación OAuth2**: Integración nativa con el sistema central `csdocs_core`.
- ✅ **Búsqueda Avanzada**: Indexación y búsqueda eficiente de documentos.
- ✅ **API RESTful**: Documentación completa con Swagger para integraciones.
- ✅ **Procesamiento en Segundo Plano**: Gestión de notificaciones y clasificación vía Queues (Redis).
- ✅ **Soporte Híbrido DB**: Uso de MySQL para datos relacionales y MongoDB para metadatos flexibles.

---

## ⚙️ Requisitos Previos

### Software Requerido

- **PHP**: ^8.1
- **Extensiones PHP**: `json`, `zip`, `gd`, `bcmath`, `xml`, `mbstring`, `mongodb`
- **Gestor de Dependencias**: [Composer](https://getcomposer.org/)
- **Base de Datos**: MySQL 8.x + MongoDB 4.x/5.x
- **Cache & Queues**: [Redis](https://redis.io/)

### Credenciales de Acceso

- Acceso al sistema **Core** (csdocs_core) configurado y funcionando.
- Credenciales de bases de datos (MySQL y MongoDB).

---

## 🚀 Instalación Rápida

### 1. Clonar el Repositorio

```bash
cd /var/www/html/
git clone git@bitbucket.org:csdocs/archivisticaback.git
cd archivisticaback
```

### 2. Instalar Dependencias

```bash
composer install
```

### 3. Configurar Entorno

```bash
# Copiar archivo de entorno
cp .env.example .env

# Configurar permisos
chmod -R 775 storage bootstrap/cache
```

### 4. Configurar Base de Datos

Asegúrate de tener creadas las bases de datos en MySQL y MongoDB según lo configurado en tu `.env`. Luego ejecuta:

```bash
php artisan migrate --seed
php artisan storage:link
```

---

## 🔧 Configuración Detallada

### Paso 1: Configurar Archivo .env

> [!IMPORTANT]
> Edita el archivo `.env` y configura las variables `DB_*`, `MONGO_*` y `REDIS_*`. Asegúrate de que `CACHE_DRIVER`,
`SESSION_DRIVER` y `QUEUE_CONNECTION` apunten a `redis` para un rendimiento óptimo.

### Paso 2: Copiar Credenciales OAuth desde Core

> [!IMPORTANT]
> Dado que la administración, sesiones y login son gestionados por la aplicación `csdocs_core`, **no** debes ejecutar
`passport:install`. En su lugar, debes copiar los archivos `oauth-private.key` y `oauth-public.key` desde el directorio
`storage/` del proyecto `csdocs_core` hacia el directorio `storage/` de este proyecto.

```bash
# Copiar las llaves OAuth del sistema Core
cp ../csdocs-core/storage/oauth-private.key storage/
cp ../csdocs-core/storage/oauth-public.key storage/
```

---

## 🌐 Configuración de Core

```ini
# En tu .env configurar el acceso a la BD del sistema central:
DB_CORE_DATABASE = csdocs_core_cg
END_POINT_CORE = http://localhost:8002
```

---

## 📦 Gestión de Queues (Colas)

Para procesar notificaciones y tareas pesadas, ejecuta los siguientes workers:

### Notificaciones por Email

```bash
php artisan queue:work redis --queue=EmailNotification --sleep=3 --tries=1
```

---

## 🛠️ Comandos Útiles

### Desarrollo y Mantenimiento

```bash
# Limpiar cachés y optimizar
php artisan optimize:clear

# Generar documentación API (Swagger)
php artisan l5-swagger:generate

# Respaldar MongoDB
php artisan mongodb:backup

# Ver rutas disponibles
php artisan route:list
```

---

## 🔍 Solución de Problemas

### Problema: Error "Class not found" o cambios no reflejados

```bash
composer dump-autoload
php artisan optimize:clear
```

### Problema: Error de llaves OAuth

Verifica que las llaves copiadas desde el Core tengan los permisos correctos:

```bash
ls -la storage/oauth-*.key
chmod 600 storage/oauth-*.key
```

### Problema: Conexión a MongoDB fallida

Asegúrate de tener instalada la extensión `mongodb` en PHP y que el servicio esté corriendo.

---

## 📊 Estado del Proyecto

- **Versión:** 1.0.0
- **Laravel:** 10.x
- **PHP:** 8.1.x
- **MySQL:** 8.x
- **MongoDB:** compatible con 4.x/5.x
- **Entorno:** Local / Producción

---

## 📝 Notas Importantes

⚠️ **IMPORTANTE:**

- Este proyecto es estrictamente dependiente del sistema **Core**.
- El cumplimiento de la **Ley de Archivo** reside en la correcta jerarquía de las series y subseries configuradas.
- Mantener sincronizadas las llaves OAuth es vital para el acceso de los usuarios.

---

**Desarrollado por:** [CSDocs]  
**Documentación:** Archivística

---

<p align="center">
✨ <strong>Archivística - Sistema de Gestión Documental y Archivonomía</strong> ✨
</p>
