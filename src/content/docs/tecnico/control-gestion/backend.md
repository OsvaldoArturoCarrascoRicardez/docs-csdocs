---
title: Control de Gestión Backend
---

## 📋 Tabla de Contenidos

- [Descripción del Proyecto](#-descripción-del-proyecto)
- [Características](#-características)
- [Requisitos Previos](#-requisitos-previos)
- [Instalación Rápida](#-instalación-rápida)
- [Configuración Detallada](#-configuración-detallada)
- [Gestión de Queues (Colas)](#-gestión-de-queues-colas)
- [Comandos Útiles](#-comandos-útiles)
- [Solución de Problemas](#-solución-de-problemas)

---

## 📖 Descripción del Proyecto

**Control de Gestión** es una plataforma robusta diseñada para facilitar y agilizar la comunicación interna y el flujo
de trabajo dentro de dependencias gubernamentales u organizaciones con estructuras jerárquicas complejas.

El sistema permite la gestión integral de **"Asuntos"**, los cuales actúan como el núcleo de la comunicación
institucional. Estos asuntos pueden ser creados, seguidos y **turnados** (asignados) dinámicamente entre diferentes
Unidades Organizacionales según la jerarquía establecida, permitiendo un control preciso sobre el despacho y tratamiento
de cada solicitud.

Una de sus características principales es el potente módulo de **generación de "Oficios"**, que ofrece una interfaz
intuitiva similar a procesadores de texto (estilo Word). Estos oficios pueden ser enviados y generados automáticamente
como nuevos asuntos, asegurando que cada documento oficial tenga un seguimiento administrativo riguroso hasta su
ejecución o resolución final.

---

## ✨ Características

- ✅ **Comunicación Interna Eficiente**: Gestión de asuntos y turnados entre unidades.
- ✅ **Módulo de Oficios Estilo Word**: Creación y edición de documentos oficiales sin salir del sistema.
- ✅ **Estructura Jerárquica**: Organización basada en unidades organizacionales dinámicas.
- ✅ **Autenticación OAuth2**: Integración nativa con el sistema central `csdocs_core`.
- ✅ **Procesamiento en Segundo Plano**: Gestión de notificaciones vía Queues (Redis).
- ✅ **API RESTful**: Base sólida para la integración con el frontend y servicios externos.

---

## ⚙️ Requisitos Previos

### Software Requerido

- **PHP**: ^8.1
- **Extensiones PHP**: `json`, `zip`, `gd`, `bcmath`, `xml`, `mbstring`
- **Gestor de Dependencias**: [Composer](https://getcomposer.org/)
- **Base de Datos**: MySQL 8.x
- **Cache & Queues**: [Redis](https://redis.io/)

### Credenciales de Acceso

- Acceso al sistema **Core** (csdocs_core) configurado y funcionando.
- Credenciales de base de datos MySQL local.

---

## 🚀 Instalación Rápida

### 1. Clonar el Repositorio

```bash
cd controlgestionback
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

### 4. Configurar Base de Datos y Storage

Asegúrate de tener creada la base de datos en MySQL según lo configurado en tu `.env`. Luego ejecuta:

```bash
php artisan migrate --seed

php artisan storage:link
```

---

## 🔧 Configuración Detallada

### Paso 1: Configurar Archivo .env

> [!IMPORTANT]
> Edita el archivo `.env` y configura las variables `DB_*` y `REDIS_*`. Asegúrate de que `CACHE_DRIVER`,
`SESSION_DRIVER` y `QUEUE_CONNECTION` (o `QUEUE_DRIVER`) apunten a `redis`.

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

Para procesar notificaciones y tareas pesadas, ejecuta el siguiente worker:

### Notificaciones por Email

```bash
php artisan queue:work redis --queue=EmailNotification --sleep=3 --tries=1
```

```bash
php artisan queue:work redis --queue=ClasificacionArchivistica --sleep=3 --tries=1
```

---

## 🛠️ Comandos Útiles

### Desarrollo y Mantenimiento

```bash
# Limpiar cachés y optimizar
php artisan optimize:clear

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

---

## 📊 Estado del Proyecto

- **Versión:** 2.0.0
- **Laravel:** 10.x
- **PHP:** 8.1.x
- **MySQL:** 8.x
- **Entorno:** Local / Producción

---

## 📝 Notas Importantes

⚠️ **IMPORTANTE:**

- Este proyecto es estrictamente dependiente del sistema **Core**.
- Mantener sincronizadas las llaves OAuth es vital para el acceso de los usuarios.

---

**Desarrollado por:** [CSDocs]  
**Documentación:** Control de Gestión

---

<p align="center">
✨ <strong>Control de Gestión - Sistema de Comunicación y Trámite Administrativo</strong> ✨
</p>
