---
title: Core Frontend
---

Este proyecto es la interfaz de administración central (Core) de la suite **CSDocs**. Funciona como la piedra angular del ecosistema, centralizando la gestión de información compartida entre las diferentes aplicaciones de la suite.

## Suite CSDocs

La suite está integrada por soluciones especializadas que cubren todo el ciclo de vida de la información y los procesos administrativos:

### 🛡️ Core (Piedra Angular)

Es el motor central de la suite que gestiona la configuración global:

- **Gestión Centralizada**: Usuarios, dominios, instancias, licencias y clientes.
- **Estructura Organizacional**: Configuración de unidades y compañías.
- **Control de Acceso**: Vinculación de usuarios con aplicaciones y dominios específicos.

### 📝 Control Gestión (CG)

Especializada en la gestión de correspondencia y seguimiento de solicitudes:

- **Ciclo de Vida de Asuntos**: Generación y seguimiento de asuntos internos o externos.
- **Generación Documental**: Creación de oficios automatizados.

### 📂 Content (Gestor Documental)

Un potente repositorio documental multi-tenant con capacidades avanzadas de gestión de archivos, control de versiones y colaboración.

### 🏛️ Archivística

Gestión integral del marco archivístico institucional, controlando fases de trámite, concentración e histórico.

---

## 📋 Tabla de Contenidos

- [Características Principales](#-características-principales)
- [Guía de Desarrollo](#-guía-de-desarrollo)
- [Configuración de Entornos](#-configuración-de-entornos)
- [Uso de Agentes de IA](#-uso-de-agentes-de-ia)

---

## ✨ Características Principales

- ✅ **Gestión Global**: Administración de todo el ecosistema CSDocs desde un solo punto.
- ✅ **Angular 20**: Construido con la última tecnología de Google.
- ✅ **Gestión de Licencias**: Control centralizado de licencias y accesos.
- ✅ **Multi-Tenant**: Soporte para múltiples instancias y dominios.

---

## 🛠️ Guía de Desarrollo

### Requisitos Previos

- **Node.js**: v22 (Recomendado usar `nvm use 22`)
- **Angular CLI**: v20.3.13

### Instalación de Dependencias

```bash
npm install --legacy-peer-deps
```

### Servidor de Desarrollo

Ejecuta `ng serve` para un servidor local. Navega a `http://localhost:4200/`. La aplicación se recargará automáticamente al modificar los archivos.

### Construcción

Ejecuta `ng build` para compilar el proyecto. Los archivos resultantes se guardarán en el directorio `dist/`.

---

## 🔧 Configuración de Entornos

El frontend requiere apuntar correctamente a la API del backend:

1. Localiza el archivo de configuración de ejemplo: `public/config.example.json`.
2. Copia este archivo y renómbralo como `config.json` en el mismo directorio.
3. Modifica la propiedad `apiUrl` para que apunte a tu instancia de **Core Back**:

```json
{
  "production": false,
  "apiUrl": "http://localhost:8000"
}
```

---

## 🤖 Uso de agentes de IA

- Las políticas y reglas para el uso de agentes de IA están centralizadas en `AGENTS.MD`.
- Antes de usar un agente o aceptar cambios generados por IA, revisa `AGENTS.MD` y sigue el proceso de revisión descrito.

---

**Desarrollado por:** [CSDocs]
**Documentación:** Core Front

---

<p align="center">
✨ <strong>Core CSDocs - Motor Central de la Suite</strong> ✨
</p>
