---
title: Content Frontend
---

**Content Light Front** es la interfaz de usuario moderna diseñada para la gestión integral de documentos. Construida sobre **Angular 18**, permite gestionar archivos, visualizar documentos y administrar clasificaciones de manera eficiente.

## Suite CSDocs

La suite CSDocs está integrada por soluciones especializadas interconectadas:

### 🛡️ Core

Motor central que gestiona la autenticación y configuración global.

### 📂 Content (Gestor Documental)

Repositorio documental avanzado:

- **Explorador Inteligente**: Operaciones completas de archivos (crear, mover, copiar).
- **Visor PDF Integrado**: Visualización rápida sin salir de la plataforma.
- **Multitenant**: Gestión de múltiples instancias y repositorios.

---

## 📋 Tabla de Contenidos

- [Características Principales](#-características-principales)
- [Guía de Desarrollo](#-guía-de-desarrollo)
- [Configuración de Estilos](#-configuración-de-estilos)
- [Configuración de Entornos](#-configuración-de-entornos)
- [Uso de Agentes de IA](#-uso-de-agentes-de-ia)

---

## ✨ Características Principales

- ✅ **Angular 18 & Material Design**: Interfaz reactiva y moderna.
- ✅ **Gestión Global de Estado**: Implementado con `@ngrx/store`.
- ✅ **Reportes Visuales**: Gráficos interactivos con Chart.js.
- ✅ **Diseño Responsivo**: Adaptable a cualquier dispositivo.

---

## 🛠️ Guía de Desarrollo

### Requisitos Previos

- **Node.js**: v20.x (Recomendado usar `nvm use 20`)
- **Angular CLI**: v18.x

### Instalación de Dependencias

```bash
npm install --legacy-peer-deps
```

### Servidor de Desarrollo

Ejecuta `ng serve` para iniciar el servidor en `http://localhost:4203/`.

### Construcción

Ejecuta `ng build` para generar los artefactos de producción en `dist/`.

---

## 🎨 Configuración de Estilos

Para personalizar la paleta de colores:

1. Copia `src/assets/scss/_material.example.scss` a `src/assets/scss/_material.scss`.
2. Actualiza los valores hexadecimales con tu identidad corporativa.

---

## 🔧 Configuración de Entornos

Configura las URLs de los servicios en `src/environments/environment.ts`:

```typescript
export const environment = {
    production: false,
    apiUrl: "http://localhost:8000", // URL del backend Content
    // Otras configuraciones...
};
```

---

## 🤖 Uso de agentes de IA

- Las políticas y reglas para el uso de agentes de IA están centralizadas en `AGENTS.MD`.
- Revisa `AGENTS.MD` antes de aplicar cambios automatizados.

---

**Desarrollado por:** [CSDocs]
**Documentación:** Content Light Front

---

<p align="center">
✨ <strong>Content Light - Gestión Documental Ágil</strong> ✨
</p>
